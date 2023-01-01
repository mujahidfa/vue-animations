<script setup lang="ts">
import { routes } from "../routes";
</script>

<template>
  <header>
    <header>
      <nav>
        <ul>
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li v-for="{ routeName, displayName } in routes" :key="routeName">
            <NuxtLink :to="routeName">{{ displayName }}</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
  </header>
  <main>
    <slot></slot>
  </main>
</template>
