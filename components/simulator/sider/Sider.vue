<script setup>
const selected = ref(0);
const category = ref("");
const toggle = ref(false);

function setToggle() {
  toggle.value = !toggle.value;
}

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
};
console.log(options["Free Flight"][1]);
</script>

<template>
  <div
    :class="selected === 1 ? 'bg-gray-500' : 'bg-[#2D4C9A]'"
    class="w-[350px] hidden text-[#f5f5f5] relative p-5 flex flex-col"
  >
    <div class="mx-auto">
      <p class="font-bold">Pilot's name</p>
    </div>
    <div
      class="font-bold text-2xl flex gap-6 flex-col mx-auto mt-60 text-center cursor-pointer"
    >
      <p
        class="hover:text-blue-500"
        @click="[setSelected(1), setCategory('Free Flight')]"
      >
        Free Flight
      </p>
      <p
        @click="[setSelected(1), setCategory('Flight Challenges')]"
        class="hover:text-blue-500"
      >
        Flight Challenges
      </p>
      <UChip
        class="hover:text-blue-500"
        color="yellow"
        @click="[setSelected(1), setCategory('Assignments')]"
        ><p>Assignments</p></UChip
      >
      <p
        @click="[setSelected(1), setCategory('Options')]"
        class="hover:text-blue-500"
      >
        Options
      </p>
      <p class="hover:text-blue-500">Exit</p>
    </div>
    <UIcon
      name="i-heroicons-arrow-right"
      color="black"
      class="h-[40px] w-[50px] bg-black relative left-[300px] bottom-[150px] cursor-pointer"
    ></UIcon>
  </div>
  <div
    v-if="selected == 1"
    class="bg-[#2D4C9A] relative w-[400px] h-screen p-5 flex flex-col text-2xl text-[#f5f5f5] items-center"
  >
    <div class="mt-[265px] flex gap-6 flex-col items-center h-screen">
      <p
        class="hover:bg-gray-500"
        v-for="option in options[category][selected]"
      >
        {{ option }}
      </p>
      <p
        class="fixed bottom-4 cursor-pointer hover:bg-gray-500"
        @click="setSelected(0)"
      >
        Back
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
