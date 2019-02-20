<template>
    <div>
        <span>已经完成</span>
        <span>{{this.doneMsg.length}}</span>
        <!-- <span>done已接收到doneMsg数据：{{doneMsg}}</span><br>
        <span>done接收到的doingList数组：{{doingList}}</span> -->
        <ol>
            <li v-for="(doneData,index) in doneMsg" :key=index>
                <listItem :msg = doneData :flag = flag @deleteItem="handledeleteDoneChosen(index,flag)" @checkChange="handleCheckChange(index,flag)" />
            </li>
        </ol>

    </div>
</template>

<script>
import listItem from '@/components/listItem.vue'
    export default {
        name:"done",
        components:{
            listItem,
        },
        props:{
            doneMsg:{
                type:Array,
                default:[],
            },
            doingList:{
                type:Array,
                default:[],
            },
        },
        data(){
            return{
                doneList:[],
                flag:false,
            }
        },
        methods:{
            handledeleteDoneChosen(index,flag){
                if(flag === false){
                    this.doneMsg.splice(index,1);
                }
                
            },
            handleCheckChange(index,flag){
                if(flag === false){
                    this.doingList.splice(index,0,this.doneMsg[index]);
                    console.log("doinglist-->" + this.doingList);
                    this.doneMsg.splice(index,1);
                }
            }
        }
    }
</script>

<style scoped>

</style>