<script setup>
import FoodfCard from './components/FoofCard.vue'
</script>

<template>
  <main>
    <h1 class="title">今日何食べる？</h1>
    <FoodfCard />
    <p>vs</p>
    <FoodfCard />
  </main>
</template>

<style scoped>
main {
  width: 350px;
  margin: 100px auto;
  text-align: center;
}

.title {
  margin-bottom: 60px;
}
</style>
