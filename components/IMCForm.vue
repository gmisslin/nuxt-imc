<template>
  <section
    class="p-6 max-w-xl mx-auto bg-white rounded-xl shadow-lg flex flex-col"
  >
    <h2 class="text-2xl leading-7 font-semibold">
      Pour calculer votre IMC, veuillez remplir vos informations
    </h2>

    <div class="mt-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="weight">
        Weight
      </label>
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="weight"
        type="number"
        placeholder="Weight"
        v-model="weight"
      />
    </div>

    <div class="mt-4 mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="height">
        Height
      </label>
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="height"
        type="number"
        placeholder="Height"
        v-model="height"
      />
    </div>

    <button
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      @click="calculateIMC"
    >
      Button
    </button>
  </section>
</template>

<script>
export default {
  name: "IMCForm",
  data() {
    return {
      weight: 0,
      height: 0,
    };
  },
  methods: {
    calculateIMC() {
      console.log("calculate imc");
      const imc = this.weight / this.height ** 2;
      this.$emit("sendIMC", imc.toFixed(2));
    },
  },
};
</script>
