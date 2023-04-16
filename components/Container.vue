<script setup lang="ts"></script>

<template>
  <div class="container">
    <code>
      <slot name="left"></slot>
    </code>
    <slot name="right"></slot>
  </div>
</template>

<style scoped>
.container {
  display: flex-reverse;
  flex-direction: column-reverse;
}
</style>
