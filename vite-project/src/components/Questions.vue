<script setup>
import { ref,defineEmits,defineProps } from 'vue';

const props= defineProps(['questions','index1','correct'])
const emit=defineEmits(['statusNo'])
function statusNo(status){
    emit('statusNo',status)
   
}

function reset(){
  index1.value=0;


}
const index1=ref(0)


</script>
<template>
    <div>
        
                <div 
                    v-for="question,index in questions" 
                    :key="index" 
                    v-show="index1==index"
                >

                <div>
                    {{ question.q }}
                </div>
            
 
                <div  @click="statusNo(answer.status)" 

                    v-for="answer,ind in question.answers" 

                    :key="ind"
                > 
                    {{ answer.option }}
                </div>
            <!-- <div >{{ correct }}</div> -->
            <div>Result: {{ correct }}</div>
                </div><br>

<button v-show="index1<questions.length-1" @click="index1++">next</button> <br>
<button @click="reset" v-if="index1==questions.length-1">reset</button>


<p v-if="index1==questions.length">{{ correct }}<button @click="reset">reset</button></p><br>
<!-- <button></button> -->

    </div>
</template>
<style scoped></style>