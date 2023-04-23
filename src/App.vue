<script setup>
import Menu from "./components/lesson_2/2.2.slot-props/Menu.vue";
import MenuButton from "./components/lesson_2/2.2.slot-props/MenuButton.vue";
import MenuItems from "./components/lesson_2/2.2.slot-props/MenuItems.vue";
import MenuItem from "./components/lesson_2/2.2.slot-props/MenuItem.vue";
</script>

<template>
  <div @click="open">Click on the below menu : </div>
  <Menu v-slot="{ open, close }">
    <MenuButton>Actions</MenuButton>
    <MenuItems>
      <MenuItem v-slot="{ active }">
        <span :class="{ active }"> Edit </span>
      </MenuItem>
      <MenuItem v-slot="{ active }">
        <span :class="{ active }"> Update </span>
      </MenuItem>
      <MenuItem v-slot="{ active }">
        <span :class="{ active }"> Add </span>
      </MenuItem>
      <MenuItem v-slot="{ active }">
        <span :class="{ active }" @click="close"> Intended option </span>
      </MenuItem>
    </MenuItems>
  </Menu>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
