<template>
    <form @submit.prevent="submitExpense">
      <input v-model="title" placeholder="Expense Title" required />
      <input v-model.number="amount" placeholder="Amount" required />
      <button type="submit">Add Expense</button>
    </form>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'ExpenseForm',
    emits: ['add-expense'],
    setup(props, { emit }) {
      const title = ref('');
      const amount = ref(0);
  
      const submitExpense = () => {
        emit('add-expense', { title: title.value, amount: amount.value });
        title.value = '';
        amount.value = 0;
      };
  
      return {
        title,
        amount,
        submitExpense,
      };
    },
  };
  </script>
  