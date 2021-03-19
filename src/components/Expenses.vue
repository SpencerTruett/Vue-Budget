<template>
  <v-card>
    <v-form @submit.prevent="handleSubmit">
      <v-text-field v-model="name" type="text" outlined />
      <v-text-field v-model="amount" type="number" outlined />
      <v-btn type="submit">Submit</v-btn>
    </v-form>
  </v-card>
</template>

<script>
export default {
  props: ["expenses"],
  data() {
    return {
      name: "",
      amount: 0
    }
  },
  methods: {
    handleSubmit() {
      this.$emit("expense-added", { name: this.name, amount: +this.amount });
      this.name = "";
      this.amount = 0;
    }
  }
}
</script>

<style>
</style>