<template>
  <section
    class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-lg flex items-center flex-col"
  >
    <h2 class="text-2xl leading-7 font-semibold">
      Welcome to your Nuxt Application
    </h2>

    <NuxtLink to="/imc">Click here to check your IMC</NuxtLink>
  </section>
</template>

<script>
export default {
  name: "welcome",
};
</script>
