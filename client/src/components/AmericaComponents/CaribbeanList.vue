<template>
  <div class="caribbean-list" v-if="countryFrom === 'caribbean'">
    <h2>Caribbean</h2>
    <ul>
      <list-component v-for="(country, index) in filterCountry" :country="country" :key="index"></list-component>
    </ul>
  </div>
</template>

<script>
import { eventBus } from "@/main.js";
import ListComponent from "@/helpers/ListComponent.vue";
export default {
  name: "caribbean-list",
  props: ["countries", "country", 'countryFrom'],
  components: {
    "list-component": ListComponent
  },
  methods: {},
  computed: {
    filterCountry() {
      return this.countries.filter(country => {
        return country.subregion === "Caribbean";
      });
    }
  }
};
</script>

<style>
</style>