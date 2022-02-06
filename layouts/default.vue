<template>
  <div>
    <Navbar :navItems="navItems" />
    <Nuxt />
  </div>
</template>

<script lang="ts">
import type { navItem } from "~/components/Navbar";

import Vue from "vue";

const navItems: navItem[] = [
  { label: "home", link: "/" },
  { label: "inspire", link: "/inspire" },
  { label: "routing", link: "/happy-id" },
];
export default Vue.extend({
  data(): { navItems: navItem[] } {
    return {
      navItems: navItems,
    };
  },
});
</script>