<template>
  <q-page class="flex flex-center">
    Setup page
  </q-page>
</template>

<style>
</style>

<script lang='ts'>
import Vue from "vue";
import Component from "vue-class-component";

@Component({ name: "Setup" })
export default class Setup extends Vue {
  constructor() {
      super();

      console.log('setup page');
  }
}
</script>
