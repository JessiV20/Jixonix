<script setup>
import MainLayout from '../layouts/MainLayout.vue'
import HomePro from '../components/HomePro.vue';
import WebIcon from '../components/icons/WebIcon.vue';
import MobileIcon from '../components/icons/MobileIcon.vue';
import IaIcon from '../components/icons/IaIcon.vue';
</script>

<template>
  <MainLayout>
    <section class="relative h-screen flex items-center justify-center text-center px-6 text-white overflow-hidden" >
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,rgba(168,85,247,0.15),transparent_60%)]"></div>
      <div class="relative z-10 max-w-4xl">
        <h1 class="text-5xl md:text-6xl font-bold leading-tight mb-6">
          Soluciones digitales hechas a la 
          <span class="text-purple-400">medida de tu negocio.</span>
        </h1>
        <p class="text-gray-400 text-lg mb-10">
          Creo soluciones digitales seguras y funcionales adaptadas a las necesidades de tu empresa.
        </p>
        <div class="flex justify-center gap-4">
          <router-link to="/services" class="px-6 py-3 rounded-full bg-purple-600 hover:bg-purple-500 transition font-medium"
          >
            Empezar ahora
          </router-link>

          <router-link to="/contact" class="px-6 py-3 rounded-full border border-white/20 hover:bg-white/5 transition"
          >
            Contactanos →
          </router-link>
        </div>
      </div>
    </section>

    <section class="relative py-12 px-6 text-white overflow-hidden" >
      <div class="relative max-w-7xl mx-auto">
        <div class="text-center mb-20">
          <span class="inline-flex items-center gap-2 px-4 py-2 mb-6 rounded-full
            bg-white/5 border border-white/10text-sm text-gray-300">
            🧩 Servicios
          </span>
          <h2 class="text-4xl md:text-5xl font-bold mb-6">
            Construimos el sistema
            <span class="text-purple-400">que tu negocio necesita</span>
          </h2>
          <p class="text-gray-400 max-w-2xl mx-auto text-lg">
            Diseñamos, desarrollamos y escalamos productos digitales con tecnología de alto nivel.
          </p>
        </div>
        <div class="grid md:grid-cols-3 gap-10">
          <HomePro
            title="Desarrollo Web"
            description="Plataformas modernas, rápidas y escalables enfocadas en conversión y experiencia de usuario."
            link="/services"
          >
            <WebIcon class="w-8 h-8 text-sky-400"/>
          </HomePro>

          <HomePro
            title="Apps Móviles"
            description="Aplicaciones iOS y Android con alto rendimiento, seguridad y UX impecable."
            link="/services"
          >
            <MobileIcon class="w-8 h-auto text-gray-300"/>
          </HomePro>

          <HomePro
            title="IA & Automatización"
            description="Optimizamos procesos con inteligencia artificial, analítica avanzada y automatización."
            link="/services"
          >
            <IaIcon class="w-8 h-8 text-blue-400"/>
          </HomePro>
        </div>
      </div>
    </section>
  </MainLayout>
</template>


