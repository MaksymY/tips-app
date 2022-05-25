<script setup lang="ts">
import TheIconsSet from "@/components/TheIconsSet.vue"
import WelcomeItem from '@/components/atoms/AtomInput.vue'
</script>

<template>
  <TheIconsSet/>
  <h1>Spli<br>tter</h1>
  <WelcomeItem label="Bill" type="text" placeholder="0" icon="dollar"/>
</template>

<style>
@import url('https://fonts.google.com/specimen/Space+Mono');

#app {
  font-family: 'Space Mono', sans-serif;
  margin: 0 auto;
  padding: 0;
}
</style>
