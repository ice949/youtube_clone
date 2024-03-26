<template>
  <q-layout >
    <!-- Header -->
    <q-header elevated class="header">
  <q-toolbar class="toolbar">
    <!-- First Container: Menu Button and Logo/Title -->
    <div class="container">
      <q-btn
        flat
        dense
        round
        icon="menu"
        aria-label="Menu"
        class="menu-button"
        @click="toggleLeftDrawer"
      />
      <q-toolbar-title class="toolbar-title">
        <div class="logo-title">
          <img src="../assets/youtube.png" alt="YouTube Icon" style="width: 40px;" />
          <span>YouTube</span>
        </div>
      </q-toolbar-title>
    </div>

    <div class="cont">
      <form class="search-form" @submit.prevent="performSearch">
    <div class="search-input-container">
      <q-input
        placeholder="Search"
        class="search-input"
      >
        <template v-slot:before>
          <!-- <q-icon name="search" /> -->
        </template>
        <template v-slot:after>
          <q-icon name="keyboard" />
        </template>
      </q-input>
    </div>
    <q-btn
      icon="search"
      flat
      round
      class="search-button"
    />
  </form>
  <q-btn
      icon="mic"
      flat
      round
      class="mic-button"
    />
    </div>

    <div class="container">
      <q-icon name="more_vert" class="apps-icon" />
      <div class="user_cont">
        <q-icon name="account_circle" class="profile-icon" />
        <span class="user_name">User</span>
      </div>

      <q-icon name="brightness_4" class="theme-toggle-icon" @click="toggleTheme" />
    </div>
  </q-toolbar>
</q-header>

    <q-page-container>
      <q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        bordered
        side="left"
        content-style="height: calc(100% - 64px)"
      >
        <q-list>
          <EssentialLink
            v-for="link in linksList"
            :key="link.title"
            v-bind="link"
          />
        </q-list>
      </q-drawer>

      <!-- Page Content -->
      <div class="q-page">
        <router-view />
      </div>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

defineOptions({
  name: 'MainLayout'
})

const linksList = [
  {
    title: 'Home',
    caption: 'quasar.dev',
    icon: 'home',
    link: 'https://quasar.dev'
  },
  {
    title: 'Shorts',
    caption: 'github.com/quasarframework',
    icon: 'music_note',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Shorts',
    caption: 'github.com/quasarframework',
    icon: 'videocam',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Videos',
    caption: 'chat.quasar.dev',
    icon: 'live_tv',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'History',
    caption: 'chat.quasar.dev',
    icon: 'history',
    link: 'https://chat.quasar.dev'
  }
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>

<style scoped>
.q-page {
  display: flex;
  height: 100%;
}
</style>
