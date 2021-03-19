<template>
  <v-card>
    <v-card-title>{{ title }}</v-card-title>
    <v-card-text>
      <h1 :class="dollarClass">{{ displayAmount }}</h1>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: ["title", "netAmount"],
  computed: {
    displayAmount() {
      return new Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD"
      }).format(this.netAmount);
    },
    dollarClass() {
      return {
        "green--text": this.netAmount >= 0,
        "red--text": this.netAmount < 0
      };
    }
  }
}
</script>

<style>
</style>