<template>
  <q-page class="flex flex-center">
    <img alt="Quasar logo" src="~assets/quasar-logo-full.svg">
    <button v-on:click="say()">First quasar app with TS ...</button>
  </q-page>
</template>

<style>
</style>

<script lang='ts'>
import Vue from "vue";
import Component from "vue-class-component";

@Component({ name: "Index" })
export default class Index extends Vue {
  public name: string = "index";

  private say = (): void => {
    console.log(this.name);
  };
}
</script>
