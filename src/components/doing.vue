<template>
    <div>
        <span>正在进行</span>
        <span>{{this.entryMsg.length}}</span>
        
        <ol v-for="(enter,index) in this.entryMsg" :key=index>
            <template>
                <li>
                <listItem :msg=enter :flag = flag @deleteItem ="handleDeleItem(index,flag)" @checkChange="handleCheckChange(index,flag)" />
            </li>
            </template>
            
        </ol>
    </div>   
</template>

<script>
// ./代表当前目录的下一级，要引用的文件在同一级，不能用./，可以用@，代表src目录。
import listItem from '@/components/listItem'

    export default {
        name:"doing",
        components:{
            listItem,
        },
        props:{
            entryMsg:Array,
        },
        methods:{
            handleDeleItem(index,flag){   
                if(flag === true){
                    console.log("flag的值：" + flag);
                    this.entryMsg.splice(index,1);
                    console.log("删除后--" + this.entryMsg);
                }
                
            },
            handleCheckChange(index,flag){
                if(flag === true){
                    console.log("装载数据--" + this.entryMsg[index]);
                    this.doneList.push(this.entryMsg[index]);
                    this.entryMsg.splice(index,1);  
                    this.$emit("sendBackDoneList",this.doneList);                           
                    console.log("done的值：" + this.doneList);
                }
            },
            
            
        },
        data(){
            return{
                indexNum:0,
                doneList:[],
                flag:true,
                numOfEntryMsg:0,
            }
        },
    }
</script>

<style scoped>

</style>
