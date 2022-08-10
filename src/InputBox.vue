<script setup>
import { ref, watch } from "vue";
const props = defineProps({
  modelValue: {
    type: String,
    default: "",
  },
});
const emit = defineEmits(["update:modelValue"]);
const inputValue = ref(props.modelValue);

watch(inputValue, (value) => {
  emit("update:modelValue", value);
});
</script>

<template>
  <input
    v-model="inputValue"
    type="text"
    placeholder="할 일은 많고 시간은 없고.."
  />
</template>
