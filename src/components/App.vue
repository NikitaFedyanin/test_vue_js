<template>
  <q-btn color="white" :text-color="btn_color" :label="btn_label" v-on:click="switcher"/>
</template>

<script setup>
import { ref } from 'vue'

const btn_label = ref("Primary")
const btn_color = ref("secondary")

function switcher () {
  if (btn_label.value === "Primary"){
    btn_label.value = "Amber"
    btn_color.value = "purple"
  } else {
    btn_label.value = "Primary"
    btn_color.value = "secondary"
  }
}

</script>
