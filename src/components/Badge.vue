<script setup lang="ts"></script>

<template>
  <div class="badge">
    <slot></slot>
  </div>
</template>

<style scoped>
.badge {
  box-shadow: 2px 2px 2px black;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 70px;
  height: 30px;
}

</style>