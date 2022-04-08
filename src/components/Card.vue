<script setup lang="ts"></script>

<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<style scoped>
.card {
  border-radius: 8px;
  box-shadow: 4px 4px 4px rgb(214, 214, 214);
  padding: 20px 20px;
}
</style>
