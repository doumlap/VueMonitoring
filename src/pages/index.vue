<template>
  <q-page padding class="flex content-start">
	  <div class="flex-container">
		  <q-toggle class="q-pr-sm col" padding v-model="isOnlyError" color="negative" label="Only Error" left-label />
		  <q-toggle class="q-pr-sm col" padding v-model="isOnlyWarning" color="warning" label="Only Warning" left-label />
		  <q-toggle class="q-pr-sm col" padding v-model="isOnlySuccess" color="positive" label="Only Success" left-label />
	  </div>
	  <div class="flex-container">
		  <q-card class="q-ma-sm col" inline v-for="task in activeTasks" v-bind:key="task.name">
			<q-card-title v-bind:class="{'bg-negative': task.status=='error', 'bg-positive': task.status=='success', 'bg-warning': task.status=='warning'}">
				{{task.name}}
			</q-card-title>
			<q-card-separator />
			<q-card-main>
				{{task.msg}}
			</q-card-main>
		  </q-card>
	  </div>
  </q-page>
</template>

<style>
</style>

<script lang='ts'>
import Vue from "vue";
import Component from "vue-class-component";

@Component({ name: "Index" })
export default class Index extends Vue {
  private tasks: Array<any> = new Array<any>();
  private isOnlyError: boolean = false;
  private isOnlyWarning: boolean = false;
  private isOnlySuccess: boolean = false;

  constructor() {
    super();

    console.log("index");
  }

  get activeTasks() {
    if (this.isOnlyError === true) {
      return this.tasks.filter(t => t.status === "error");
    } else if (this.isOnlyWarning === true) {
      return this.tasks.filter(t => t.status === "warning");
    } else if (this.isOnlySuccess === true) {
      return this.tasks.filter(t => t.status === "success");
    } else {
      return this.tasks;
    }
  }

  mounted() {
    this.tasks.push({
      name: "Task 1",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 2",
      status: "success",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 3",
      status: "warning",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 4",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 5",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 6",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 7",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 8",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 9",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 10",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 11",
      status: "error",
      msg: "Cannot retrieve server X"
    });
    this.tasks.push({
      name: "Task 12",
      status: "error",
      msg: "Cannot retrieve server X"
    });
  }
}
</script>
