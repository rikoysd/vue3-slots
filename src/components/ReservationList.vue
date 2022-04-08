<script setup lang="ts">
import Card from "@/components/Card.vue";
import Badge from "./Badge.vue";
</script>

<template>
  <Card class="reservation-card">
    <span>John Wick</span>
    <Badge class="vip-badge">
      <span>VIP</span>
    </Badge>
  </Card>
  <Card class="reservation-card">
    <span>Yamada Taro</span>
    <Badge class="normal-badge">
      <span>NOMAL</span>
    </Badge>
  </Card>
  <Card class="reservation-card">
    <span>Lee Sanha</span>
    <Badge class="vip-badge">
      <span>VIP</span>
    </Badge>
  </Card>
</template>

<style scoped>
.reservation-card {
  width: 400px;
  height: 60px;
  background-color: antiquewhite;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}

.vip-badge {
  background-color: rgb(216, 61, 61);
  color: white;
}

.normal-badge {
  background-color: rgb(66, 66, 202);
  color: white;
}
</style>
