<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-black text-white">
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>Zouk Needs You</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered class="bg-grey-10">
      <q-list dark separator >

        <q-item clickable @click="redirect('https://www.facebook.com/valvanessazouk/')">
          <q-icon name="groups" size="sm" />
          <div class="q-ml-lg">
            <q-item-label>Facebook</q-item-label>
            <q-item-label caption>Clique para informações</q-item-label>
          </div>
        </q-item>
        <q-item clickable @click="redirect('https://t.me/joinchat/MfblyrcuJypkYzIx')">
          <q-icon name="credit_card" size="sm" />
          <div class="q-ml-lg">
            <q-item-label>ZNY Course</q-item-label>
            <q-item-label caption>Clique para informações</q-item-label>
          </div>
        </q-item>
        <q-item clickable @click="redirect('https://t.me/joinchat/I2d7USdsYPgzZTdh')">
          <q-icon name="credit_card" size="sm" />
          <div class="q-ml-lg">
            <q-item-label>Classes</q-item-label>
            <q-item-label caption>Clique para informações</q-item-label>
          </div>
        </q-item>

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
  methods: {
    redirect(url) {
      window.open(url, '_blank');
    }
  },

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
