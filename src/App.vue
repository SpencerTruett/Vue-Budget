<template>
  <div>
    <AnnualIncome :annualIncome="annualIncome" />
  </div>
</template>

<script>
import AnnualIncome from "./components/AnnualIncome";

export default {
  components: {AnnualIncome},
  data() {
    return {
      annualIncome: 0,
      monthlyExpenses: []
    };
  }
}
</script>

<style>
</style>