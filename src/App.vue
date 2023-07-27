<script setup>
import { reactive } from "vue";

const lightIsOn = "//img.icons8.com/?size=512&id=12244&format=png";
const lightIsOff = "//img.icons8.com/?size=512&id=75&format=png";

const lightData = reactive([
  {
    title: "Light 1",
    isOn: false,
  },
  {
    title: "Light 2",
    isOn: false,
  },
  {
    title: "Light 3",
    isOn: true,
  },
]);
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Assignment</h1>
    <p class="p-5">Make These Buttons Work</p>
    <div class="flex justify-between space-x-6">
      <div class="p-10 border w-96 flex flex-col space-y-5">
        <button
          v-for="light of lightData"
          :key="light.title"
          class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          :class="light.isOn ? 'bg-blue-500' : 'bg-black'"
          @click="light.isOn = !light.isOn"
        >
          {{ light.title }} {{ light.isOn ? "On" : "Off" }}
        </button>
      </div>
      <div class="p-10 border w-96 flex flex-col space-y-5">
        <img
          v-for="light of lightData"
          :key="light.title"
          class="w-20"
          :src="light.isOn ? lightIsOn : lightIsOff"
          :alt="light.title"
        />
      </div>
    </div>
  </section>
</template>

<style scoped></style>
