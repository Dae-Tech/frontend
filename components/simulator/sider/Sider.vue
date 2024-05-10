<script setup>
import { UChip } from "#build/components";

const selected = ref(0);
const category = ref("");

function setSelected(number) {
  selected.value = number;
}

function setCategory(selectedCategory) {
  category.value = selectedCategory;
  console.log("set category");
}
const options = {
  "Free Flight": {
    1: ["Mavic 2", "Inspire"],
    2: ["Scenario 1", "Scenario 2"],
    3: ["Time of day", "Morning", "Mid-day", "Dusk", "Nigth"],
  },
  "Flight Challenges": {
    1: ["Basic movements", "Position Control"],
  },
  Assignments: {
    1: ["Company", "Flight School"],
  },
  Options: { 1: ["Display", "Sound", "Controls", "Language"] },
  Back: {
    1: (
      <UChip>
        <p>hola</p>
      </UChip>
    ),
  },
};
console.log(options["Free Flight"][1]);
</script>

<template>
  <div
    :class="selected === 1 ? 'bg-gray-500' : 'bg-[#2D4C9A]'"
    class="w-[350px] text-[#f5f5f5] relative p-5 flex flex-col"
  >
    <div class="mx-auto">
      <p class="font-bold">Pilot's name</p>
    </div>
    <div
      class="font-bold text-2xl flex gap-6 flex-col mx-auto mt-60 text-center cursor-pointer"
    >
      <p
        class="hover:bg-gray-600"
        @click="[setSelected(1), setCategory('Free Flight')]"
      >
        Free Flight
      </p>
      <p
        @click="[setSelected(1), setCategory('Flight Challenges')]"
        class="hover:bg-gray-600"
      >
        Flight Challenges
      </p>
      <UChip
        class="hover:bg-gray-600"
        color="yellow"
        @click="[setSelected(1), setCategory('Assignments')]"
        ><p>Assignments</p></UChip
      >
      <p
        @click="[setSelected(1), setCategory('Options')]"
        class="hover:bg-gray-600"
      >
        Options
      </p>
      <p class="hover:bg-gray-600">Exit</p>
    </div>
  </div>
  <div
    v-if="selected == 1"
    class="bg-[#2D4C9A] w-[400px] h-screen p-5 flex flex-col text-2xl text-[#f5f5f5] items-center"
  >
    <div class="mt-[265px] flex gap-6 flex-col">
      <p
        class="hover:bg-gray-500"
        v-for="option in options[category][selected]"
      >
        {{ option }}
      </p>
    </div>
  </div>
  <div class="bg-red-500 w-[400px] h-screen hidden">
    <p>2</p>
  </div>
  <div class="bg-red-500 w-[400px] h-screen hidden">
    <p>3</p>
  </div>
</template>
