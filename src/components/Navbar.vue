<template>
  <div class="navbar">
    <div class="navbar__wrapper">
      <div class="navbar__logo">
        <img src="@/assets/logo.svg" alt="logo">
        <span class="navbar__logo-text">Degenics</span>
      </div>
      <div class="navbar__info">
        <div class="navbar__user-info">
          <div class="navbar__user-avatar">
            <img src="@/assets/avatar.svg" alt="user-avatar">
            <div class="navbar__user-popup">
              <div class="navbar__popup">
                <div class="navbar__popup-item">
                  <img src="@/assets/logout.svg" alt="" srcset="">
                  <span>Log Out</span>
                </div>
                <div class="navbar__popup-item">
                  <img src="@/assets/wallet.svg" alt="" srcset="">
                  <span>Wallet Binding</span>
                </div>
              </div>
            </div>
          </div>
          <div class="navbar__user-details">
            <div class="navbar__user-name">
              <span>
                ACCOUNT_NAME (as : Customer)
                <button class="navbar__change-action">change</button>
                <div class="navbar__user-role">
                  <div class="navbar__popup">
                    <div class="navbar__popup-item">Customer</div>
                    <div class="navbar__popup-item">Doctor</div>
                    <div class="navbar__popup-item">Lab</div>
                    <div class="navbar__popup-item">Hospital</div>
                  </div>
                </div>
              </span>
            </div>
            <div class="navbar__user-wallet">0.000 DOT</div>
          </div>
        </div>
        <div class="navbar__notification">
          <img src="@/assets/bell.svg" alt="bell-icon">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent({

})
</script>

<style lang="scss">
  .navbar {
    width: 100%;
    height: 64px;
    background: #3F2040;

    &__wrapper {
      width: 93%;
      height: 100%;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    &__logo {
      display: flex;
      align-items: center;

      &-text {
        color: #FDC0FF;
        font-weight: 500;
        font-size: 24px;
        line-height: 28px;
        margin-left: 10px;
      }
    }

    &__info {
      display: flex;
      align-items: center;
    }

    &__user {
      position: relative;

      &-avatar {
        position: relative;
        margin-right: 19px;

        &:hover {
          .navbar__popup {
            display: flex;
          }
        }
      }

      &-details {
        position: relative;

        .navbar__popup {
          left: 105px;
        }
      }

      &-name {
        font-size: 12px;
        line-height: 14px;
        color: #FFFFFF;
      }

      &-info {
        font-weight: bold;
        display: flex;
        align-items: center;
      }

      &-wallet {
        font-size: 13px;
        line-height: 15px;
        color: #FDC0FF;
      }
    }

    &__change-action {
      font-size: 12px;
      line-height: 14px;
      color: #FDC0FF;
      border: none;
      text-decoration: underline;
      cursor: pointer;
      background: transparent;

      &:hover {
        & ~ .navbar__user-role .navbar__popup {
          display: flex;
        }
      }
    }

    &__notification {
      margin-left: 33.5px;
    }

    &__popup {
      display: none;
      position: absolute;
      left: 0;
      width: 197px;
      margin-top: 6px;
      background: #FFFFFF;
      flex-direction: column;

      &-item {
        display: inherit;
        padding: 12px 20px;
        align-items: center;
        font-size: 12px;
        line-height: 14px;
        color: #6A6868;
        gap: 18px;
      }
    }
  }
</style>
