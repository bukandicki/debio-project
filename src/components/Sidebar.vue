<template>
  <div class="sidebar">
    <div class="sidebar__links">
      <a href="#" class="sidebar__link sidebar__link--active">Dashboard</a>
      <a href="#" class="sidebar__link">Request Test</a>
      <a href="#" class="sidebar__link">Test Result</a>
      <a href="#" class="sidebar__link">Order History</a>
      <a href="#" class="sidebar__link">Documents</a>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .sidebar {
    min-width: 242px;
    height: 100vh;
    padding-left: 57px;
    padding-top: 65px;
    background: #FFFFFF;
    box-shadow: 0px 7px 20px rgba(0, 0, 0, 0.07);

    &__links {
      display: flex;
      flex-direction: column;
      gap: 21px;
    }

    &__link {
      text-decoration: none;
      font-weight: 500;
      font-size: 18px;
      line-height: 21px;
      color: #000000;

      &:hover,
      &--active {
        color: #FE008A;
      }
    }
  }
</style>
