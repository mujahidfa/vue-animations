<script setup lang="ts">
import { Motion } from "motion/vue";

const initial = { background: "var(--step0)" };
const animate = {
  background: [
    // "var(--step0)",
    "var(--step1)",
    // "var(--step2)",
    // "var(--step3)",
    // "var(--step4)",
  ],
};
const transition = {
  background: {
    duration: 10,
  },
  //   duration: 10,
  repeat: Infinity,
  //   direction: "reverse",
  easing: "ease-out",
  //   easing: ["ease-in", "linear", "ease-out"]
};
</script>

<template>
  <div class="container">
    <div class="squares">
      <div class="block" />
      <div class="block" />
      <Motion
        class="block"
        :initial="initial"
        :animate="animate"
        :transition="transition"
      />
    </div>
    <Motion
      class="background"
      :initial="initial"
      :animate="animate"
      :transition="transition"
    />
  </div>
</template>

<style scoped>
.block,
.background {
  --step0: #ff615d;
  --step1: #bad5ea;
  --step2: #fd8769;
  --step3: #356d94;
  --step4: #ffdcb3;
}

.container {
  display: flex;
  align-items: center;
  height: 100%;
  justify-content: center;
  position: relative;
}

.background {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 0;
  inset: 0;
  opacity: 0.3;
}

.squares {
  display: grid;
  height: 30vw;
  width: 30vw;
  grid-template-columns: repeat(8, 1fr);
  grid-template-rows: repeat(8, 1fr);
}

.squares > div {
  border-radius: 8px;
  overflow: hidden;
}

.squares > div:first-child,
.squares > div:nth-child(2) {
  grid-column: 1 / 6;
  grid-row: 4 / 9;
  position: relative;
  z-index: 0;
  background: rgb(255, 255, 255);
}

.squares > div:nth-child(2) {
  z-index: 1;
  opacity: 0.7;
}

.squares > div:last-child {
  grid-column: 4 / 9;
  grid-row: 1 / 6;
  position: relative;
  z-index: 0;
}
</style>
