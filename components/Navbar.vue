<template>
  <div>
    <v-navigation-drawer v-model="sidebar" app>
      <v-list>
        <v-list-item v-for="item in navItems" :key="item.label" :to="item.link">
          <v-list-item-content>{{ item.label }}</v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar>
      <span class="hidden-md-and-up">
        <v-app-bar-nav-icon @click="sidebar = !sidebar"> </v-app-bar-nav-icon>
      </span>
      <v-toolbar-title>
        <nuxt-link to="/" tag="span" style="cursor: pointer"> APP </nuxt-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-md-and-down">
        <v-btn text v-for="item in navItems" :key="item.label" :to="item.link">
          {{ item.label }}
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>
  </div>
</template>

<script lang="ts">
import type { navItem } from "./Navbar";

import Vue, { PropType } from "vue";

export default Vue.extend({
  data(): { sidebar: boolean } {
    return {
      sidebar: false,
    };
  },
  props: {
    navItems: Array as PropType<navItem[]>,
  },
});
</script>