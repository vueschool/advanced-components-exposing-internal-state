
<script setup>
import * as menu from "@zag-js/menu";
import { normalizeProps, useMachine } from "@zag-js/vue";
import { computed, ref, provide } from "vue";
const props = defineProps({
  modelValue: {
    type: String,
    default: ''
  }
})
const emit = defineEmits(['update:modelValue'])
const [state, send] = useMachine(menu.machine({
  id: "menu",
  "aria-label": "File",
  onSelect(selected) {
    emit('update:modelValue', selected.value)
  },
  closeOnSelect: false,
}));
const api = computed(() => menu.connect(state.value, send, normalizeProps), { context: { value: props.modelValue } });
provide('menu', { api, selectedId: props.modelValue })
</script>

<template>
  <div>
    <slot />
  </div>
</template>

<style>
@import './menu.css';
</style>