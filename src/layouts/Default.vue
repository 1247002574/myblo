<template>
  <div class="layout">
    <header class="page-header">
      <h1>My Blog</h1>
      <SideBar />
    </header>

    <slot style="float:right;width:80%;padding:20px" />
  </div>
</template>

<script>
import SideBar from './components/SideBar'
export default {
  name: 'LayoutPage',
  components: { SideBar },
}
</script>

<style>
.page-header {
  padding: 5rem 6rem;
  color: #fff;
  text-align: center;
  background-color: #159957;
  background-image: linear-gradient(120deg, #70b3f5, #a70684);
}
</style>
