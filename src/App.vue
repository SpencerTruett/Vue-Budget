<template>
  <v-app>
    <v-main class="pa-6 blue-grey lighten-4">
      <v-row justify="center">
        <v-col :cols="12" :md="8" :lg="4">
          <AnnualIncome :annualIncome="annualIncome" />
        </v-col>
        <v-col :cols="12" :md="6" :lg="4">
          <IncomeCard title="Monthly Net" netAmount="monthlyNet" />
        </v-col>
        <v-col :cols="12" :md="6" :lg="4">
          <IncomeCard title="Annual Net" netAmount="annualNet" />
        </v-col>
      </v-row>
      <v-row>
        <v-col :cols="12" :lg="6">
          <Expenses />
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import AnnualIncome from "./components/AnnualIncome";
import Expenses from "./components/Expenses";
import IncomeCard from "./components/IncomeCard";

export default {
  components: { 
    AnnualIncome, 
    Expenses,
    IncomeCard
    },
  data() {
    return {
      annualIncome: 0,
      monthlyExpenses: []
    };
  },
    computed: {
    monthlyIncome() {
      return this.annualIncome / 12;
    },
    totalMonthlyExpenses() {
      return this.monthlyExpenses.reduce((total, month) => {
        return total + month.amount;
      }, 0);
    },
    annualExpenses() {
      return this.totalMonthlyExpenses * 12;
    },
    monthlyNet() {
      return (this.monthlyIncome - this.totalMonthlyExpenses).toFixed(2);
    },
    annualNet() {
      return +(this.annualIncome - this.annualExpenses).toFixed(2);
    }
  }
}
</script>

<style>
</style>