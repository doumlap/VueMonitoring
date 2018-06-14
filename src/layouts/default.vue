<template>
  <q-layout view="lHh Lpr lFf">
    <q-layout-header>
      <q-toolbar
        color="primary"
        :glossy="$q.theme === 'mat'"
        :inverted="$q.theme === 'ios'"
      >
        <q-btn flat dense round aria-label="Menu"><q-icon name="menu" /></q-btn>

        <q-toolbar-title>
          Quasar App
          <div slot="subtitle">Running on Quasar v{{ $q.version }}</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-layout-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang='ts'>
import Vue from "vue";
import Component from "vue-class-component";

@Component({ name: "DefaultLayout" })
export default class DefaultLayout extends Vue {
  private leftDrawerOpen = false;

  private open = (url: string): void => {
    console.log(url);
  };
}
</script>

<style>
</style>
