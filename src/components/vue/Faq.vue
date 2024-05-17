<script setup>
import {ref} from 'vue' 

const data= ['tema 1' ,'tema 2'  ,'tema 3','tema 4' ]
const selectedIndex= ref(0)

function showInfo (i){
   if( i==selectedIndex.value){
    selectedIndex.value=-1
   }else {
    selectedIndex.value=i
   }
   
}
</script>
<template>
    <div  
    class=" select-none bg-blue-500 p-2 max-w-60 mx-auto mt-12">
        <div v-for="(theme,i) in data "
        :key="i ">
            <h1   @click="showInfo(i)" class=" hover:cursor-pointer bg-blue-400 text-white px-1 flex justify-between"
            :class="{'bg-blue-800' : selectedIndex==i}">
                {{theme}}
                <span>{{selectedIndex == i ? '-':'+'}}</span>
            </h1>
            <div v-show="selectedIndex == i" class="bg-blue-50/50  p-1 mt-1">texto del tema 1</div>
        </div>
        
    </div>
</template>