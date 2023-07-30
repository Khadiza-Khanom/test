<script setup>
import{ref,reactive} from 'vue'
import Questions from "./components/Questions.vue" 
import Result from "./components/Result.vue" 

const questions=reactive([
  {
    q:'1.what is 5+5?',
    answers:[{
      option:'10',
      status: true
    },
    {
      option:'11',
    status: false
  },
  {
    option:'12',
    status: false
  }]
  },
  {
    q:'2.what is  1+1?',
    answers:[{
      option:'3',
      status: false
    },
    {
      option:'2',
    status: true
  },
  {
    option:'4',
    status: false
  }]
  },
  {
    q:'3.what  is 4+6?',
    answers:[{
      option:'112',
      status: false
    },
    {
      option:'213',
    status: false
  },
  {
    option:'10',
    status: true
  }]
  },
  {
    q:' 4.What is 9+0?',
    answers:[{
      option:'12',
      status: false
    },
    {
      option:'345',
    status: false
  },
  {
    option:'9',
    status: true
  }]
  }
])


const correct=ref(0)



function statusNo(status){
  if(status){
  correct.value++
}
  
  }




</script>

<template>
  <Questions
  :questions="questions"

  :correct="correct"
  @statusNo="statusNo"
 
  
  />
  <Result/>
</template>

<style scoped>

</style>
