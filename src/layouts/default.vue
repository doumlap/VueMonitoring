<template>
  <q-layout view="hHr LpR lFf">
    <q-layout-header>
      <q-toolbar color="primary" :glossy="$q.theme === 'mat'" :inverted="$q.theme === 'mat'">
        <q-btn flat dense round aria-label="Menu" @click="mini=!mini">
          <q-icon name="menu"></q-icon>
        </q-btn>
        <q-toolbar-title>
          <router-link to="/">Monitoring</router-link>
          <div slot="subtitle">Running on Quasar v{{ $q.version }}</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-layout-header>

    <q-layout-drawer :mini="mini" side="left" v-model="drawerOpen">
      <q-list separator>
        <q-item to="/" link exact>
          <q-item-main label="Dashboard"></q-item-main>
        </q-item>
        <q-item to="/setup" link exact>
          <q-item-main label="Setup"></q-item-main>
        </q-item>
      </q-list>
    </q-layout-drawer>

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
  private drawerOpen: boolean = true;
  private mini: boolean = true;
}
</script>

<style>
</style>
