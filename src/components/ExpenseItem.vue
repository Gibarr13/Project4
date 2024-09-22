<template>
    <li>
      {{ expense.title }}: ${{ expense.amount }}
    </li>
  </template>
  
  <script>
  export default {
    name: 'ExpenseItem',
    props: {
      expense: {
        type: Object,
        required: true,
      },
    },
  };
  </script>
  