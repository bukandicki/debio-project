<template>
  <div class="currency">
    <input type="text" placeholder="Search currency..." class="currency__search-box" v-model="searchQuery">
    <table class="currency__list">
      <tr>
        <th>Name</th>
        <th>Unit</th>
        <th>Value</th>
        <th>Type</th>
      </tr>
      <template v-if="filteredCurrencies?.length">
        <tr v-for="(currency, idx) in filteredCurrencies" :key="idx">
          <td>{{ currency.name }}</td>
          <td>{{ currency.unit }}</td>
          <td>{{ currency.value }}</td>
          <td>{{ currency.type }}</td>
        </tr>
      </template>
      <tr v-else>
        <td colspan="4" class="currency__not-found">
          <h3>Currencies Not Found</h3>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import { defineComponent, onMounted, computed, reactive, toRefs } from 'vue'
export default defineComponent({
  setup () {
    const state = reactive({
      currencies: [],
      searchQuery: ''
    })

    const fetchCurrencies = async () => {
      fetch('https://api.coingecko.com/api/v3/exchange_rates').then(async response => {
        const { rates } = await response.json()

        state.currencies = Object.values(rates)
      })
    }

    const filteredCurrencies = computed(() => {
      const filter = state.currencies.filter(currency => {
        return state.searchQuery.toLowerCase().split(' ').every(v => currency.name.toLowerCase().includes(v))
      })

      return filter
    })

    onMounted(async () => {
      await fetchCurrencies()
    })

    return {
      ...toRefs(state),
      fetchCurrencies,
      filteredCurrencies
    }
  }
})
</script>

<style lang="scss">
  .currency {
    table, td, th {
      border: 1px solid #ddd;
      text-align: left;
    }

    table {
      border-collapse: collapse;
      width: 100%;
    }

    th, td {
      padding: 15px;
    }

    &__search-box {
      padding: 8px;
      font-size: 1.2em;
      margin-bottom: 12px;
    }

    &__not-found {
      text-align: center !important;
    }
  }
</style>
