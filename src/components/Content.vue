<template>
  <div class="content">
    <h4>Dashboard</h4>

    <section>
      <div class="content__list">
        <Card title="Request Test">
          <template v-slot:icon>
            <img src="@/assets/dna.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>Get your DNA samples tested</p>
          </template>
        </Card>
        <Card title="Download Genome">
          <template v-slot:icon>
            <img src="@/assets/genome.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>Download your genomic file</p>
          </template>
        </Card>
        <Card title="Upload EMR">
          <template v-slot:icon>
            <img src="@/assets/emr.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>Upload your EMR file</p>
          </template>
        </Card>
      </div>

      <div class="content__list">
        <Card title="Exercise">
          <template v-slot:icon>
            <img src="@/assets/gym.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
              <span class="content__badge content__badge--sending">Sending</span>
            </div>
          </template>
        </Card>
        <Card title="Covid 19" description="ABCD-1234-HJKL">
          <template v-slot:icon>
            <img src="@/assets/covid.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
              <span class="content__badge content__badge--recieved">Recieved</span>
            </div>
          </template>
        </Card>
        <Card title="Supplement" description="ABCD-1234-HJKL">
          <template v-slot:icon>
            <img src="@/assets/supplement.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
              <span class="content__badge content__badge--success">Success</span>
            </div>
          </template>
        </Card>
        <button class="content__button">Show all orders</button>
      </div>

      <div class="content__list">
        <Card title="Supplement" description="Get your DNA samples tested">
          <template v-slot:icon>
            <img src="@/assets/supplement.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
            </div>
          </template>
        </Card>
        <Card title="Genetic Traits" description="Download your genomic file">
          <template v-slot:icon>
            <img src="@/assets/genome.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
            </div>
          </template>
        </Card>
        <Card title="Exercise" description="Upload your EMR file">
          <template v-slot:icon>
            <img src="@/assets/apple.svg" alt="" srcset="">
          </template>
          <template v-slot:desc>
            <p>ABCD-1234-HJKL</p>
            <strong>Lab 1</strong>
            <div class="content__list-details">
              <p>January 2 2021</p>
            </div>
          </template>
        </Card>
        <button class="content__button">Show all result</button>
      </div>
    </section>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import Card from '@/components/Card.vue'

export default defineComponent({
  components: { Card }
})
</script>

<style lang="scss">
  .content {
    width: 100%;
    height: 100vh;
    padding: 32px 40px;
    background: #E5E5E5;

    &__button {
      border: none;
      border-radius: 3px;
      font-weight: bold;
      font-size: 14px;
      line-height: 16px;
      text-align: center;
      cursor: pointer;
      background: #FE2F96;
      color: #FFFFFF;
      padding: 10px 0;

      &:focus {
        outline: none;
      }
    }

    &__list {
      display: flex;
      flex-direction: column;
      gap: 15px;

      &-details {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }
    }

    &__badge {
      padding: 2px 15px;
      border-radius: 10px;
      margin-left: 20px;

      &--sending {
        background: #c09cae;
        color: #FFFFFF;
      }

      &--recieved {
        background: #75DEE4;
        color: #FFFFFF;
      }

      &--success {
        background: #52FFB6;
        color: #FFFFFF;
      }
    }

    section {
      display: flex;
      justify-content: space-between;
    }
  }
</style>
