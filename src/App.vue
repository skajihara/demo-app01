<script setup>
import { ref } from 'vue'
import FoodfCard from './components/FoofCard.vue'
const foods = ref([
  { name: '寿司', emoji: '🍣' },
  { name: 'ハンバーガー', emoji: '🍔' },
  { name: '焼肉', emoji: '🥩' },
  { name: '麺系', emoji: '🍜' },
  { name: 'たこ焼き', emoji: '🐙' },
  { name: 'おでん', emoji: '🍢' },
  { name: '丼系', emoji: '🍚' },
  { name: 'オムライス', emoji: '🥚' },
  { name: 'イタリアン', emoji: '🍕' },
  { name: '中華料理', emoji: '🥟' },
  { name: 'とんかつ', emoji: '🐖' },
  { name: '韓国料理', emoji: '🧇' },
  { name: 'カレーライス', emoji: '🍛' },
  { name: '鍋系', emoji: '🍲' },
  { name: '居酒屋', emoji: '🍶' },
  { name: 'ファミレス', emoji: '🍽️' }
])
const pickedFoodIndex = ref(0)
const newFoodIndex = ref(1)
function pickedFood(index) {
  pickedFoodIndex.value = index
  newFoodIndex.value++
}
</script>

<template>
  <main>
    <h1 class="title">今日何食べる？</h1>
    <FoodfCard
      :name="foods[pickedFoodIndex].name"
      :emoji="foods[pickedFoodIndex].emoji"
      @click="pickedFood(pickedFoodIndex)"
    />
    <template v-if="newFoodIndex < foods.length">
      <p>VS</p>
      <FoodfCard
        :name="foods[newFoodIndex].name"
        :emoji="foods[newFoodIndex].emoji"
        @click="pickedFood(newFoodIndex)"
      />
    </template>
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
