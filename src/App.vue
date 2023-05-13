<script setup>
import { ref } from "vue";
import Menu from "./components/lesson_3/legacy-model/Menu.vue";
import MenuButton from "./components/lesson_3/legacy-model/MenuButton.vue";
import MenuItems from "./components/lesson_3/legacy-model/MenuItems.vue";
import MenuItem from "./components/lesson_3/legacy-model/MenuItem.vue";

const menuItems = ["Edit", "Update", "Add", "Intended option"]
const selected = ref('')
</script>

<template>
  <div>Click on the below menu : </div>
  <Menu v-model="selected">
    <MenuButton>{{ 'Actions' }}</MenuButton>
    <MenuItems>
      <MenuItem v-for="item in menuItems" :key="item">
        <span :class="{ active: item === selected }"> {{ item }} </span>
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

.container {
  display: flex;
  width: 100%;
  /* flex-direction: column; */
}

.left {
  flex: 1
}

.right {
  flex: 1
}
</style>
