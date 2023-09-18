<template>
  <section class="h-full">
    <div class="accounts-container">
      <AccountCard v-for="account in accounts" :key="account" />

      <AddAccountBtn @click="addAccount" />
    </div>
  </section>
</template>

<script setup lang="ts">
useHead({
  titleTemplate: '%s - Julio 2023' // TODO: add to the title the active month/year
})

const accounts = ref<any[]>([1])

/** */
function addAccount () {
  accounts.value.push(accounts.value.length + 1)
}
</script>

<style scoped lang="scss">
.accounts-container {
  gap: 24px;
  height: 100%;
  display: flex;
  padding: 48px 32px;
  overflow-x: auto;
  // TODO: center scroll on mobile
}
</style>
