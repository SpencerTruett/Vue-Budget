<template>
  <v-app>
    <v-main class="pa-6 blue-grey lighten-4">
      <v-row justify="center">
        <v-col :cols="12" :md="8" :lg="4">
          <AnnualIncome :annualIncome="annualIncome" />
        </v-col>
        <v-col :cols="12" :md="6" :lg="4">
          <IncomeCard title="Monthly Annual" netAmount="100" />
        </v-col>
        <v-col :cols="12" :md="6" :lg="4">
          <IncomeCard title="Annual Net" netAmount="-1" />
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
  }
}
</script>

<style>
</style>