<script setup lang="ts">
import Card from "@/components/Card.vue";
import { ref } from "vue";
import Badge from "./Badge.vue";
import MosaicResevation from "@/components/MosaicReservation.vue";
import ReservationList from "@/components/ReservationList.vue";

const isCalenderVisible = ref(true);

const onClickButton = () => {
  isCalenderVisible.value = !isCalenderVisible.value;
};
</script>

<template>
  <div class="container">
    <Card class="menu-card">
      <span>Badges</span>
      <div class="badges">
        <Badge class="vip-badge">
          <span>VIP</span>
        </Badge>
        <Badge class="normal-badge">
          <span>NOMAL</span>
        </Badge>
      </div>
    </Card>

    <div v-if="isCalenderVisible">
      <ReservationList></ReservationList>
    </div>

    <div v-else>
      <MosaicResevation></MosaicResevation>
    </div>

    <button @click="onClickButton">Change</button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.menu-card {
  width: 300px;
  height: 80px;
  background-color: #ccc;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 24px;
}

.badges {
  display: flex;
  justify-content: space-between;
  width: 60%;
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
