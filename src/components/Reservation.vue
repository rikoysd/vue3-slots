<script setup lang="ts">
import Card from "@/components/Card.vue";
import { ref } from "vue";
import Badge from "./Badge.vue";
import MosaicResevation from "@/components/MosaicReservation.vue";
import ReservationList from "@/components/ReservationList.vue";

const isCalenderVisible = ref(true);
const isDialogOpen = ref(false);

const onClickButton = () => {
  // isCalenderVisible.value = !isCalenderVisible.value;
  isDialogOpen.value = !isDialogOpen.value;
};

const getContent = () => {
  if (isCalenderVisible.value) {
    return ReservationList;
  } else {
    return MosaicResevation;
  }
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
    <!-- 複数のタブで画面を切り替える場合は以下の方法が使える -->
    <component :is="getContent()"></component>

    <!-- v-ifを使う方法 -->
    <!-- <div v-if="isCalenderVisible">
      <ReservationList></ReservationList>
    </div>
    <div v-else>
      <MosaicResevation></MosaicResevation>
    </div> -->

    <button @click="onClickButton">Change</button>
    <teleport to="body">
      <dialog class="dialog" :open="isDialogOpen">
        <span>Dialog</span>
      </dialog>
    </teleport>
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

.dialog {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  height: 200px;
  width: 400px;
  margin: auto;
  background-color: aliceblue;
}
</style>
