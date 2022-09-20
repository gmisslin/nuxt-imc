<template>
  <section
    class="p-6 max-w-xl mx-auto bg-white rounded-xl shadow-lg flex flex-col"
    v-if="imc > 0"
  >
    <h2 class="text-2xl leading-7 font-semibold">Votre IMC est de {{ imc }}</h2>
    <h2 class="text-2xl leading-7 font-semibold">
      Ce qui peut s'interpreter par
      <span class="text-red-500">{{ interpretation }}</span>
    </h2>
  </section>
</template>

<script>
export default {
  name: "IMCResult",
  props: {
    imc: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      // interpretation
    };
  },
  computed: {
    interpretation() {
      let result = "";
      if (this.imc < 16.5) {
        result = "dénutrition";
      } else if (this.imc >= 16.5 && this.imc < 18.5) {
        result = "maigreur";
      } else if (this.imc >= 18.5 && this.imc < 25) {
        result = "poids normal";
      } else if (this.imc >= 25 && this.imc < 30) {
        result = "surpoids";
      } else if (this.imc >= 30 && this.imc < 35) {
        result = "obésité modérée";
      } else if (this.imc >= 35 && this.imc < 40) {
        result = "obésité sévère";
      } else {
        result = "obésité morbide ou massive";
      }

      return result;
    },
  },
  methods: {
    calculateIMC() {
      console.log("calculate imc");
      const imc = this.weight * this.height ** 2;
      console.log(imc);
    },
  },
};
</script>
