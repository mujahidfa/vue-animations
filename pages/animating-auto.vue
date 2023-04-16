<script setup lang="ts">
import { ref } from "vue";
import { Motion } from "motion/vue";
import { useElementSize } from "@vueuse/core";

const motionRef = ref<InstanceType<typeof Motion> | null>(null);
const { width: motionWidth } = useElementSize(motionRef);
const isClicked = ref(false);

const code = `
<script setup lang="ts">
import { ref } from "vue";
import { Motion } from "motion/vue";
import { useElementSize } from "@vueuse/core";

const motionRef = ref<InstanceType<typeof Motion> | null>(null);
const { width: motionWidth } = useElementSize(motionRef);
const isClicked = ref(false);
<\/script>

<template>
  <div class="container">
    <div class="main" @click="isClicked = !isClicked">
      <Motion
        ref="motionRef"
        class="fill"
        :animate="{ width: isClicked ? '100%' : '0%' }"
        :transition="{ duration: 0.6 }"
      />
      <div class="content">{{ motionWidth.toFixed(0) }}</div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  height: 100%;
  justify-content: center;
}
.main {
  position: relative;
  width: 200px;
  height: 50px;
  cursor: pointer;
  border-radius: 5px;
  border: 2px solid #272727;
  overflow: hidden;
}
.fill {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: hotpink;
}
.content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #272727;
}
</style>

`.trim();
</script>

<template>
  <Container>
    <template #left>
      {{ code }}
    </template>
    <template #right>
      <div class="container">
        <div class="main" @click="isClicked = !isClicked">
          <Motion
            ref="motionRef"
            class="fill"
            :animate="{ width: isClicked ? '100%' : '0%' }"
            :transition="{ duration: 0.6 }"
          />
          <div class="content">{{ motionWidth.toFixed(0) }}</div>
        </div>
      </div>
    </template>
  </Container>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  height: 100%;
  justify-content: center;
}
.main {
  position: relative;
  width: 200px;
  height: 50px;
  cursor: pointer;
  border-radius: 5px;
  border: 2px solid #272727;
  overflow: hidden;
}
.fill {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: hotpink;
}
.content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #272727;
}
</style>
