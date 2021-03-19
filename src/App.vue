<template>
  <div>
    <AnnualIncome :annualIncome="annualIncome" />
    <Expenses />
  </div>
</template>

<script>
import AnnualIncome from "./components/AnnualIncome";
import Expenses from "./components/Expenses";

export default {
  components: { 
    AnnualIncome, 
    Expenses
    },
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