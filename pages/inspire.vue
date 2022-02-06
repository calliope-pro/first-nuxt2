<template>
  <div style="text-align: center;">
    <v-btn @click="plus()">{{cnt}}は{{numberOfAho}}</v-btn>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      cnt: 0,
    };
  },
  computed: {
    numberOfAho(): string {
      return this.cnt % 3 ? "普通です" : "あばっばばばっば";
    },
  },
  methods: {
    plus() {
      this.cnt++;
    },
  },
});
</script>