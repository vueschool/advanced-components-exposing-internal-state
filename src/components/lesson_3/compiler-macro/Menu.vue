<script setup>
import * as menu from "@zag-js/menu";
import { normalizeProps, useMachine } from "@zag-js/vue";
import { computed, provide } from "vue";

const modelValue = defineModel()

const [state, send] = useMachine(menu.machine({
  id: "menu",
  "aria-label": "File",
  onSelect(selected) {
    modelValue.value = selected.value;
  },
  closeOnSelect: false,
}));
const api = computed(() => menu.connect(state.value, send, normalizeProps), { context: { value: modelValue.value } });

provide('menu', { api, selectedId: modelValue.value })
</script>

<template>
  <div>
    <slot />
  </div>
</template>

<style>
@import './menu.css';
</style>