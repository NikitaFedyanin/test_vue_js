<template>
  <q-banner v-if="is_primary" rounded class="bg-red-8 text-white">Включен Primary</q-banner>
  <q-btn class="fixed-center" color="white" v-bind="btn_attrs" :label="btn_label" @click="switcher"/>
</template>

<script setup>
import { ref, reactive, computed } from 'vue'

// reactive работает с Map, List, делая сам объект реактивным
const btn_attrs = reactive({
  'text-color': "secondary",
})

// Оборачивает значение в реактивный объект
const btn_label = ref("Primary")


// computed возвращает ref вычисляемого свойства
const is_primary = computed(() => {
  return btn_label.value === "Primary" ? true : false
})



function switcher () {
  if (btn_label.value === "Primary"){
    btn_label.value = "Amber"
    btn_attrs["text-color"] = "purple"
  } else {
    btn_label.value = "Primary"
    btn_attrs["text-color"] = "secondary"
  }
}

</script>
