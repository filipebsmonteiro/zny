<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-labelheader>
          Essential Links
        </q-item-labelheader>

        <a class="q-item q-item-type row no-wrap q-item--clickable q-link cursor-pointer q-focusable q-hoverable" tabindex="0" href="https://quasar.dev" target="_blank">
        <div class="q-focus-helper" tabindex="-1"></div>
        <div class="q-item__section column q-item__section--side justify-center q-item__section--avatar">
          <i class="q-icon notranslate material-icons" aria-hidden="true" role="presentation">school</i>
        </div>
        <div class="q-item__section column q-item__section--main justify-center">
          <div class="q-item__label">Docs</div>
          <div class="q-item__label q-item__label--caption text-caption">quasar.dev</div>
        </div>
        </a>

      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {},

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
