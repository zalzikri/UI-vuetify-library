<template>
  <VApp>
    <SideBar @selectOption="onSelectOption"/>
    <VMain>
      <Gambar :isWithColor="isWithColor"/>
    </VMain>
  </VApp>

</template>

<script setup>
import SideBar from "./components/SideBar.vue"
import Gambar from "./components/Gambar.vue"
import {ref} from "vue"

const isWithColor=ref(true)
const onSelectOption=(isColor)=>{isWithColor.value=isColor; console.log(isWithColor.value)}
</script>
