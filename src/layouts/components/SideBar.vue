<template>
  <div>
    <div class="sidebar" style="border:1px solid black;padding:5px">
      <span v-for="(item, index) in constantRouterMap" :key="index">
        <g-link :to="item.path">{{ item.icon }} {{ item.title }}</g-link>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  data() {
    return {
      constantRouterMap: [
        {
          path: '/news',
          icon: '☆',
          title: '最新动态',
        },
        {
          path: '/social',
          icon: '♂',
          title: '社交圈',
        },
        {
          path: '/',
          icon: '♀',
          title: '博客列表',
        },
        {
          path: '/kaiyuan',
          icon: '◇',
          title: '开源项目',
        },
      ],
    }
  },
}
</script>
