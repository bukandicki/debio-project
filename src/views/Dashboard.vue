<template>
  <div class="dashboard">
    <Navbar />
    <section>
      <Sidebar />
      <Content />
    </section>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import Navbar from '@/components/Navbar.vue'
import Sidebar from '@/components/Sidebar.vue'
import Content from '@/components/Content.vue'

export default defineComponent({
  components: { Navbar, Sidebar, Content }
})
</script>

<style lang="scss" scoped>
  section {
    display: flex;
  }
</style>
