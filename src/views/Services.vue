<script setup>
import MainLayout from '../layouts/MainLayout.vue'
import ServicePro from '../components/ServicePro.vue'
import WebIcon from '../components/icons/WebIcon.vue';
import MobileIcon from '../components/icons/MobileIcon.vue';
import IaIcon from '../components/icons/IaIcon.vue';
</script>


<template>
  <MainLayout>
    <section
      class="relative min-h-screen py-32 px-6
             text-white overflow-hidden"  >
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,rgba(168,85,247,0.18),transparent_60%)]"></div>

      <div class="relative max-w-4xl mx-auto text-center mb-24">
        <span
          class="inline-flex items-center px-4 py-2 mb-6 rounded-full
                 bg-white/5 border border-white/10 text-sm text-gray-300"
        >
          ⚡ Servicios
        </span>

        <h1 class="text-5xl md:text-6xl font-bold mb-6">
          Construimos el sistema que 
          <span class="text-purple-400">tu negocio necesita</span>
        </h1>

        <p class="text-gray-400 text-lg">
          Tecnología moderna, performance extremo y diseño que comunica valor.
        </p>
      </div>

      <div class="relative max-w-7xl mx-auto grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        <ServicePro
          title="Desarrollo Web"
          description="Aplicaciones web rápidas, seguras y escalables con tecnologías modernas."
          :features="[
            'Plataformas responsive y modernas',
            'Optimización SEO y rendimiento',
            'Integración con APIs y sistemas existentes',
            'Diseño UX/UI enfocado en conversión',
            'Mantenimiento y soporte continuo'
          ]"
        >
          <template #icon>
            <WebIcon class="w-12 h-12 text-sky-400" />
          </template>
        </ServicePro>

        <ServicePro
          title="Aplicaciones Móviles"
          description="Apps nativas y multiplataforma con experiencia de usuario impecable."
          :features="[
            'iOS y Android nativos o multiplataforma',
            'Interfaz intuitiva y atractiva',
            'Notificaciones y sincronización en tiempo real',
            'Seguridad y escalabilidad',
            'Mantenimiento y soporte continuo'
          ]"
        >
          <template #icon>
            <MobileIcon class="w-12 h-12 text-purple-400" />
          </template>
        </ServicePro>

        <ServicePro
          title="Inteligencia Artificial"
          description="Automatización, análisis predictivo y soluciones basadas en datos."
          :features="[
            'Automatización de procesos repetitivos',
            'Análisis predictivo y decisiones basadas en datos',
            'Chatbots y asistentes inteligentes',
            'Integración con sistemas existentes',
            'Mantenimiento y soporte continuo'
          ]"
        >
          <template #icon>
            <IaIcon class="w-12 h-12 text-blue-400" />
          </template>
        </ServicePro>

      </div>

    </section>
  </MainLayout>
</template>

