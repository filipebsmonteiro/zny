<template>
  <q-page class="flex column flex-center">
    <FlipCard only-horizontal hide-print-button hide-flip-button>
      <template v-slot:card-front class="row">
        <div class="flex-center">

          <div class="flex justify-center">
            <h2 class="text-bold q-mt-xs q-mb-md">ZNY COURSE</h2>

            <div class="items-center">
              <template v-if="cursos === 0">
                <q-icon v-for="i in 10" :key="i" size="md" color="warning" name="star_outline" />
              </template>

              <template v-else>
                <q-icon v-for="i in cursos" :key="i" size="md" color="warning" name="star_rate" />

                <q-icon v-if="cursos > Math.floor(cursos)" size="md" color="warning" name="star_half" />

                <q-icon v-for="i in 10 - cursos" :key="i" size="md" color="warning" name="star_outline" />
              </template>
            </div>
          </div>


          <div class="flex justify-between q-mx-md">
            <h4 class="seventy">{{ nome }}</h4>
            <img src="~assets/img/VAL-E-VANESSA_LOGO.png" style="width: 30%;" />
          </div>

          <div class="flex justify-between q-mx-md">
            <p class="seventy">Issued in {{ local }}</p>
            <img src="~assets/img/ZNY-logo.png" width="150"/>
          </div>

        </div>
      </template>
    </FlipCard>

    <q-input v-model="cursos" label="Quantidade de Cursos" class="q-mt-lg">
      <template v-slot:prepend>
        <q-btn flat @click="() => {cursos--}" icon-right="remove" />
      </template>
      <template v-slot:append>
        <q-btn flat @click="() => {cursos++}" icon-right="add" />
      </template>
    </q-input>
    <q-input v-model="nome" label="Seu nome" maxlength="28" class="q-mt-md"/>
    <q-input v-model="local" label="Local do último curso" class="q-mt-md"/>

  </q-page>
</template>

<script>
import FlipCard from 'src/components/FlipCard.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  components: {FlipCard},
  data() {
    return {
      cursos: 0,
      nome: null,
      local: 'Rio de Janeiro'
    }
  }
})
</script>

<style scoped>
:deep(.flip-card-front) {
  color: white !important;
  background: #232526;
  background: -webkit-linear-gradient(to right, #414345, #232526);
  background: linear-gradient(to right, #414345, #232526);
}

.q-field {
  min-width: 50%;
}

.seventy {
  white-space: nowrap;
  max-width: 70% !important;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
