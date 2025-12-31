<script setup>
defineProps({
  title: String,
  description: String,
  features: Array, 
})
</script>

<template>
  <div
    class="group relative p-10 rounded-3xl
           bg-white/5 backdrop-blur-xl
           border border-white/10
           transition-all duration-500
           hover:-translate-y-3 hover:shadow-[0_30px_80px_-20px_rgba(168,85,247,0.45)]"
  >
    <div
      class="absolute inset-0 rounded-3xl opacity-0 group-hover:opacity-100
             bg-[radial-gradient(circle_at_top,rgba(168,85,247,0.15),transparent_60%)]
             transition-opacity duration-500"
    ></div>

    <div class="relative z-10 text-start">

      <div
        class="text-5xl mb-6 w-16 h-16 flex items-center justify-center
               rounded-xl bg-purple-500/20 text-purple-400
               group-hover:scale-110 transition-transform duration-300"
      >
        <slot name="icon" />
      </div>

      <h3 class="text-2xl font-bold mb-4">{{ title }}</h3>

      <p class="text-gray-400 mb-6">{{ description }}</p>


      <ul class="mb-6 text-gray-300 list-disc list-inside space-y-2">
        <li v-for="(feature, index) in features" :key="index">{{ feature }}</li>
      </ul>

      <router-link
        to="/contact"
        class="flex items-center text-sm text-purple-400 font-medium group-hover:underline"
      >
        <span>Solicitar cotización</span>
        <span class="ml-2 transform transition-transform group-hover:translate-x-2">→</span>
      </router-link>
    </div>
  </div>
</template>
