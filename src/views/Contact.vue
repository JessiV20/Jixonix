<script setup>
import MainLayout from "../layouts/MainLayout.vue";
import { ref } from "vue";
import emailjs from "emailjs-com";

const formRef = ref(null);
const loading = ref(false);
const modal = ref(false);
const modalMessage = ref("");

const sendEmail = async () => {
  loading.value = true;
  try {
    await emailjs.sendForm(
      "service_yucd6e9",
      "template_unnqdpp",
      formRef.value,
      "uuDvvv4dAeBJL2ZIi"
    );
    modalMessage.value = "Correo enviado exitosamente";
    modal.value = true;
    formRef.value.reset();
  } catch (error) {
    console.error(error);
    modalMessage.value = "Error al enviar el correo ❌";
    modal.value = true;
  } finally {
    loading.value = false;
  }
};

const closeModal = () => {
  modal.value = false;
};
</script>

<template>
  <MainLayout>
    <section
      class="relative min-h-screen py-32 px-6 text-white overflow-hidden"
    >
      <div
        class="absolute inset-0 bg-[radial-gradient(circle_at_left,rgba(168,85,247,0.18),transparent_60%)]"
      ></div>

      <div
        class="relative max-w-7xl mx-auto grid gap-20 md:grid-cols-2 items-start"
      >
        <div>
          <span
            class="inline-flex items-center gap-2 px-4 py-2 mb-6 rounded-full bg-white/5 border border-white/10 text-sm text-gray-300"
          >
            📬 Contáctanos
          </span>
          <h1 class="text-5xl md:text-6xl font-bold mb-6">
            Pongámonos en <span class="text-purple-400">contacto</span>
          </h1>
          <p class="text-gray-400 text-lg mb-10 max-w-xl">
            Escríbenos para resolver dudas, solicitar una demo o empezar a
            construir una solución digital a la medida de tu negocio.
          </p>
          <ul class="space-y-4 text-gray-300">
            <li class="flex items-center gap-3">
              <span
                class="w-6 h-6 flex items-center justify-center rounded-full bg-purple-500/20 text-purple-400"
                >✓</span
              >
              Agenda una llamada con nuestro equipo
            </li>
            <li class="flex items-center gap-3">
              <span
                class="w-6 h-6 flex items-center justify-center rounded-full bg-purple-500/20 text-purple-400"
                >✓</span
              >
              Descubre el plan ideal para tu proyecto
            </li>
            <li class="flex items-center gap-3">
              <span
                class="w-6 h-6 flex items-center justify-center rounded-full bg-purple-500/20 text-purple-400"
                >✓</span
              >
              Solicita una demo o asesoría técnica
            </li>
          </ul>
        </div>

        <form
          ref="formRef"
          @submit.prevent="sendEmail"
          class="relative bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-10 space-y-6"
        >
          <div class="grid md:grid-cols-2 gap-6">
            <div>
              <label class="text-sm text-gray-300 mb-2 block">Nombre</label>
              <input
                type="text"
                name="nombre"
                placeholder="Juan"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
                required
              />
            </div>
            <div>
              <label class="text-sm text-gray-300 mb-2 block">Apellido</label>
              <input
                type="text"
                name="apellido"
                placeholder="Pérez"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
                required
              />
            </div>
          </div>

          <div class="grid md:grid-cols-2 gap-6">
            <div>
              <label class="text-sm text-gray-300 mb-2 block">Tema</label>
              <select
                name="tema"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
                required
              >
                <option class="bg-[#120f24] text-white" value="General">
                  General
                </option>
                <option class="bg-[#120f24] text-white" value="Desarrollo Web">
                  Desarrollo Web
                </option>
                <option class="bg-[#120f24] text-white" value="Apps Móviles">
                  Apps Móviles
                </option>
                <option
                  class="bg-[#120f24] text-white"
                  value="IA & Automatización"
                >
                  IA & Automatización
                </option>
                <option class="bg-[#120f24] text-white" value="Soporte">
                  Soporte
                </option>
              </select>
            </div>
            <div>
              <label class="text-sm text-gray-300 mb-2 block">Correo</label>
              <input
                type="email"
                name="email"
                placeholder="tu@email.com"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
                required
              />
            </div>
          </div>

          <div class="grid md:grid-cols-2 gap-6">
            <div>
              <label class="text-sm text-gray-300 mb-2 block">Empresa</label>
              <input
                type="text"
                name="empresa"
                placeholder="Tech Solutions"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
              />
            </div>
            <div>
              <label class="text-sm text-gray-300 mb-2 block"
                >Tamaño del equipo</label
              >
              <select
                name="tamano_equipo"
                class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
              >
                <option class="bg-[#120f24] text-white" value="1–10">
                  1–10
                </option>
                <option class="bg-[#120f24] text-white" value="11–50">
                  11–50
                </option>
                <option class="bg-[#120f24] text-white" value="51–200">
                  51–200
                </option>
                <option class="bg-[#120f24] text-white" value="200+">
                  200+
                </option>
              </select>
            </div>
          </div>
          <div>
            <label class="text-sm text-gray-300 mb-2 block"
              >¿Cómo podemos ayudarte?</label
            >
            <textarea
              name="mensaje"
              rows="5"
              placeholder="Cuéntanos sobre tu proyecto..."
              class="w-full p-4 rounded-xl bg-white/5 text-white border border-white/10 focus:outline-none focus:ring-2 focus:ring-purple-500"
              required
            ></textarea>
          </div>

          <div
            class="flex flex-col md:flex-row items-center justify-between gap-4 pt-4"
          >
            <p class="text-sm text-gray-400">
              O escríbenos a
              <a
                href="mailto:jixonix.contacto@gmail.com"
                class="text-purple-400 hover:underline"
                >jixonix.contacto@gmail.com</a
              >
            </p>
            <button
              type="submit"
              class="px-8 py-3 rounded-full bg-purple-600 hover:bg-purple-500 transition font-medium flex items-center justify-center gap-2"
            >
              <span v-if="!loading">Enviar mensaje</span>
              <svg
                v-else
                class="animate-spin h-5 w-5 text-white"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
              >
                <circle
                  class="opacity-25"
                  cx="12"
                  cy="12"
                  r="10"
                  stroke="currentColor"
                  stroke-width="4"
                ></circle>
                <path
                  class="opacity-75"
                  fill="currentColor"
                  d="M4 12a8 8 0 018-8v4a4 4 0 00-4 4H4z"
                ></path>
              </svg>
            </button>
          </div>
        </form>
      </div>
    </section>

    <div
      v-if="modal"
      class="fixed inset-0 flex items-center justify-center bg-black/50 z-50"
    >
      <div class="bg-white rounded-xl p-8 max-w-sm w-full text-center">
        <div class="flex justify-center mb-4">
          <svg
            v-if="modalMessage.includes('exitosamente')"
            class="h-12 w-12 text-purple-600"
            fill="currentColor"
            viewBox="0 0 20 20"
          >
            <path
              fill-rule="evenodd"
              d="M16.707 5.293a1 1 0 00-1.414 0L8 12.586 4.707 9.293a1 1 0 00-1.414 1.414l4 4a1 1 0 001.414 0l8-8a1 1 0 000-1.414z"
              clip-rule="evenodd"
            />
          </svg>
          <svg
            v-else
            class="h-12 w-12 text-red-600"
            fill="currentColor"
            viewBox="0 0 20 20"
          >
            <path
              fill-rule="evenodd"
              d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-11V7a1 1 0 10-2 0v2a1 1 0 102 0zm0 4a1 1 0 10-2 0 1 1 0 002 0z"
              clip-rule="evenodd"
            />
          </svg>
        </div>

        <p class="text-gray-800 mb-6">{{ modalMessage }}</p>
        <button
          @click="closeModal"
          class="px-6 py-2 rounded-full bg-purple-600 hover:bg-purple-500 text-white font-medium transition"
        >
          Cerrar
        </button>
      </div>
    </div>
  </MainLayout>
</template>
