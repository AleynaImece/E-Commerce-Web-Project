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

        <q-toolbar-title> Quasar App </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>
        <component-link
          v-for="link in componentLinks"
          :key="link.title"
          v-bind="link"
        >
        </component-link>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ComponentLink, {
  ComponentLinkProps,
} from 'components/ComponentLink.vue';

const componentLinks: ComponentLinkProps[] = [
  {
    title: 'Ana Sayfa',
    caption: 'quasar.dev',
    icon: 'school',
    link: '/',
  },
  {
    title: 'Sayfa 2',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: '/page2',
  },
  {
    title: 'sayfa 3',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: '/page3',
  },
  {
    title: 'sayfa 4',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: '/page4',
  },
  {
    title: 'sayfa 5',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: '/page5',
  },
  {
    title: 'sayfa 6',
    caption: 'quasar.dev',
    icon: 'school',
    link: '/page6',
  },
  {
    title: 'sayfa 7',
    caption: 'Carousel',
    icon: 'school',
    link: '/page7',
  },
  {
    title: 'sayfa 8',
    caption: 'Carousel',
    icon: 'school',
    link: '/page8',
  },
  {
    title: 'sayfa 9',
    caption: 'Carousel',
    icon: 'school',
    link: '/page9',
  },
  {
    title: 'sayfa 10',
    caption: 'Carousel',
    icon: 'school',
    link: '/page10',
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
