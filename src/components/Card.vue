<template>
  <div class="card">
    <div class="card__wrapper">
      <div class="card__icon" v-if="$slots['icon']">
        <slot name="icon"></slot>
      </div>

      <div class="card__details">
        <div class="card__title">{{ title }}</div>
        <div class="card__description" v-if="$slots['desc']">
          <slot name="desc"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    title: { type: String, default: 'Default Title' },
    description: { type: String, default: 'Default Description' }
  }
})
</script>

<style lang="scss">
  .card {
    min-width: 305px;
    min-height: 110px;
    background: #FFFFFF;
    border-radius: 10px;
    padding: 30px 41px;
    display: flex;

    &__wrapper {
      width: 100%;
      display: flex;
      align-items: center;
    }

    &__details {
      width: 100%;
      margin-left: 25px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    &__title {
      font-weight: 500;
      font-size: 18px;
      line-height: 21px;
      margin-bottom: 5px;
      color: #000000;
    }

    &__description {
      font-weight: 500;
      font-size: 12px;
      line-height: 14px;
      color: #595959;
    }
  }
</style>
