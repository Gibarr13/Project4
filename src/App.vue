<template>
  <div id="app">
    <h1>Expense Tracker</h1>
    <ExpenseForm @add-expense="addExpense" />
    <ExpenseList :expenses="expenses" />
  </div>
</template>

<script>
import { ref } from 'vue';
import ExpenseForm from './components/ExpenseForm.vue';
import ExpenseList from './components/ExpenseList.vue';

export default {
  name: 'App',
  components: {
    ExpenseForm,
    ExpenseList,
  },
  setup() {
    const expenses = ref([]);

    const addExpense = (expense) => {
      expenses.value.push(expense);
    };

    return {
      expenses,
      addExpense,
    };
  },
};
</script>
