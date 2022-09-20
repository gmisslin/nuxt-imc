<template>
  <section>
    <IMCForm @sendIMC="receiveIMC" />
    <IMCResult :imc="imc" />
  </section>
</template>

<script>
export default {
  name: "IMC",
  data() {
    return {
      imc: 0,
    };
  },
  methods: {
    receiveIMC(imc) {
      this.imc = imc;
    },
  },
};
</script>
