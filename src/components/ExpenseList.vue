<template>
    <ul>
      <ExpenseItem v-for="expense in expenses" :key="expense.title" :expense="expense" />
    </ul>
  </template>
  
  <script>
  import ExpenseItem from './ExpenseItem.vue';
  
  export default {
    name: 'ExpenseList',
    components: {
      ExpenseItem,
    },
    props: {
      expenses: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  