<script setup lang="ts">
import MenuItem from './MenuItem.vue'
</script>

<template>
    <h1>Menu</h1>
    <div class="menu">
        <MenuItem image="/apple.avif" bgColor="red"/>
        <MenuItem image="/banana.avif" bgColor="lightblue"/>
        <MenuItem image="/blueberry.avif" bgColor="blue"/>
        <MenuItem image="/coconut.avif" bgColor="brown"/>
        <MenuItem image="/grapefruit.avif" bgColor="orange"/>
        <MenuItem image="/lemon.avif" bgColor="yellow"/>
        <MenuItem image="/papaya.avif" bgColor="orange"/>
        <MenuItem image="/pineapple.avif" bgColor="yellow"/>
        <MenuItem image="/pomegranate.avif" bgColor="red"/>
        <MenuItem image="/raspberry.avif" bgColor="red"/>
        <MenuItem image="/kiwi.avif" bgColor="green"/>
        <MenuItem image="/watermelon.avif" bgColor="green"/>
    </div>
</template>

<style scoped>

.menu {
  display: flex;
  width: 80vw;
  flex-direction: row;
  flex-wrap: wrap;
  justify-self: center;
  background: pink;
  justify-content: center;
  gap: 2em 2em;
  padding: 2em;
}

</style>