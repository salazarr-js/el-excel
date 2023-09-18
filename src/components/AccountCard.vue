<template>
  <div class="account-card bg-gray-50 dark:bg-gray-700 shadow-xl">
    <header class="account-card__header">
      <h3>title</h3>
    </header>

    <ul class="account-records">
      <li v-for="record in records" :key="record.id">
        {{ record.description }}
      </li>
    </ul>

    <footer class="account-card__footer">
      total
    </footer>
  </div>
</template>

<script setup lang="ts">
const records = [
  { id: 1, description: '', amount: 0 }
]
</script>

<style scoped lang="scss">
$card-size: 400px;

.account-card {
  flex: 0 0 $card-size;
  width: $card-size;
  height: 100%;
  min-width: $card-size;
  border-radius: 8px;
}
</style>
