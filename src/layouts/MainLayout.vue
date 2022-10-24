<template>
  <q-layout view="hHh lpR fff">

    <q-header reveal elevated class="bg-accent text-white" height-hint="98">
      <q-toolbar :style="{ 'background-color': hex }">
        <q-toolbar-title shrink>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          Title
        </q-toolbar-title>
        <q-tabs>
          <q-route-tab to="/page1" label="Page One" />
          <q-route-tab to="/page2" label="Page Two" />
          <q-route-tab to="/page3" label="Page Three" />
        </q-tabs>
        <q-space></q-space>
        <q-btn @click="openGithub" dense round flat icon="color_lens" />
        <q-toggle color="pink" dark v-model="toggleStatus" @click="$q.dark.toggle()" />
        <q-btn-dropdown icon="color_lens">
          <q-list>
            <q-color v-model="hex" no-header class="my-picker" />
          </q-list>
        </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          Title
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const toggleStatus = ref(true)
const hex = ref('rgb(1, 56, 87)')
function openGithub(): void {
  window.open('http://www.quasarchs.com/vue-components/button#example--custom-colors', '_blank');
}
</script>
