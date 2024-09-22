<script  setup>
  import Balance from './components/Balance.vue';
  import Header from './components/header.vue';
  import {ref, computed} from 'vue';

  const transaction = ref ([
    {id: 1, text:'Paycheck', amount:700.00},
    {id: 1, text:'Water Bill', amount: -72.83},
    {id: 1, text:'Electric Bill', amount: -153.89},
    {id: 1, text:'Returned Item', amount: 20.00},
  
  ])

  const sum = computed(()=>{
    return transaction.value.reduce((acc, x)=>{
      return acc+x.amount
    },0)
  })
</script>

<template>
  <Header></Header>
  <div class="container">
    <Balance :total="sum"></Balance>
  </div>
</template>