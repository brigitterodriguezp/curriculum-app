<script setup>
import coachelaImage from './assets/img/001-coachela.png'
import concertImage from './assets/img/002-concert.png'

const personalInfo = [
  { label: 'Edad', value: '20 años' },
  { label: 'Cumpleaños', value: '21 de junio de 2005' },
  { label: 'Semestre', value: '5to semestre' },
  { label: 'Universidad', value: 'Universidad de las Fuerzas Armadas ESPE Santo Domingo' },
  { label: 'Color favorito', value: 'Azul' },
]

const interests = ['Backend', 'Programar', 'Deporte', 'K-dramas']
</script>

<template>
  <main class="min-h-screen bg-white text-slate-950">
    <section class="mx-auto flex min-h-screen w-full max-w-6xl flex-col px-5 py-6 sm:px-8 lg:px-10">
      <nav class="flex items-center justify-between border-b border-sky-200 pb-4 animate-[fadeDown_.7s_ease-out]">
        <p class="text-sm font-semibold tracking-[0.2em] text-sky-700">CV</p>
        <div class="flex items-center gap-2 text-xs font-medium uppercase tracking-[0.16em] text-slate-500">
          <span class="h-2 w-2 rounded-full bg-sky-500"></span>
          CV personal
        </div>
      </nav>

      <div class="grid flex-1 items-center gap-8 py-8 lg:grid-cols-[1.05fr_0.95fr]">
        <header class="space-y-8 animate-[fadeUp_.8s_ease-out]">
          <div class="space-y-5">
            <p class="text-sm font-medium uppercase tracking-[0.28em] text-sky-700">Curriculum personal</p>
            <div class="space-y-3">
              <h1 class="max-w-3xl text-5xl font-semibold leading-none tracking-normal text-slate-950 sm:text-6xl lg:text-7xl">
                Brigitte Rodriguez
              </h1>
              <p class="max-w-2xl text-base leading-7 text-slate-600 sm:text-lg">
                Estudiante de Ingeniería en Tecnologías de la Información y Comunicación.
                Me gusta la programación backend, practicar deporte y ver k-dramas.
              </p>
            </div>
          </div>

          <div class="grid gap-3 sm:grid-cols-2">
            <article
              v-for="(item, index) in personalInfo"
              :key="item.label"
              class="group rounded-lg border border-sky-100 bg-white p-4 shadow-sm transition duration-300 hover:-translate-y-1 hover:border-sky-300"
              :style="{ animationDelay: `${index * 120}ms` }"
            >
              <p class="text-xs font-medium uppercase tracking-[0.18em] text-slate-400">{{ item.label }}</p>
              <h2 class="mt-3 text-xl font-semibold text-slate-900">{{ item.value }}</h2>
              <div class="mt-5 h-px w-full bg-sky-100">
                <div class="h-px w-8 bg-sky-500 transition-all duration-300 group-hover:w-16"></div>
              </div>
            </article>
          </div>
        </header>

        <aside class="space-y-4 animate-[fadeUp_1s_ease-out]">
          <div class="overflow-hidden rounded-lg border border-sky-100 bg-white shadow-sm">
            <img
              :src="coachelaImage"
              alt="Foto personal"
              class="h-64 w-full object-cover sm:h-72"
            />
          </div>

          <div class="grid gap-4 sm:grid-cols-[0.95fr_1.05fr]">
            <div class="overflow-hidden rounded-lg border border-sky-100 bg-white shadow-sm">
              <img
                :src="concertImage"
                alt="Foto personal"
                class="h-full min-h-48 w-full object-cover"
              />
            </div>

            <div class="rounded-lg border border-sky-100 bg-white p-5 shadow-sm">
              <div class="flex items-center justify-between border-b border-sky-100 pb-4">
                <div>
                  <p class="text-sm text-slate-500">Carrera</p>
                  <h2 class="mt-1 text-xl font-semibold text-slate-950">Ingeniería en TIC</h2>
                </div>
                <div class="grid h-12 w-12 place-items-center rounded-full bg-sky-100 text-base font-semibold text-sky-700">
                  BR
                </div>
              </div>

              <section class="pt-5">
                <h3 class="text-sm font-semibold uppercase tracking-[0.18em] text-slate-500">Gustos</h3>
                <div class="mt-4 flex flex-wrap gap-2">
                  <span
                    v-for="interest in interests"
                    :key="interest"
                    class="rounded-full border border-sky-100 bg-sky-50 px-3 py-2 text-sm text-slate-700 transition duration-300 hover:border-sky-300 hover:text-slate-950"
                  >
                    {{ interest }}
                  </span>
                </div>
              </section>
            </div>
          </div>
        </aside>
      </div>
    </section>
  </main>
</template>
