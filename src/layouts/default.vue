<template>
  <q-layout view="hHr LpR lFf">
    <q-layout-header>
      <q-toolbar color="secondary" :glossy="true">
        <q-btn flat dense round aria-label="Menu" @click="mini=!mini">
          <q-icon name="menu"></q-icon>
        </q-btn>
        <q-toolbar-title>
          <router-link style="cursor: pointer;" tag="div" to="/">Monitoring</router-link>
          <div slot="subtitle">Running on Quasar v{{ $q.version }}</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-layout-header>

    <q-layout-drawer :mini="mini" side="left" v-model="drawerOpen">
      <q-list separator>
        <q-item to="/" link exact>
          <q-item-side color="primary" left icon="dashboard"><q-tooltip anchor="top right">Dashboard</q-tooltip></q-item-side>
          <q-item-main label="Dashboard"></q-item-main>
        </q-item>
        <q-item to="/setup" link exact>
        <q-item-side color="primary" left icon="room"><q-tooltip anchor="top right">Setup</q-tooltip></q-item-side>
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

<style lang="stylus">
@import '~variables';
</style>
