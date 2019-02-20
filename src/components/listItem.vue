<template>
    <div>
        <!-- <span>{{typeofCheck}}</span> -->
        <!-- <span>flag={{flag}}</span> -->
        <input  type="checkbox" @click= "checkChange">
        <!-- <input v-else v-model="typeofCheck" type="checkbox" @click= "doneCheckChange"> -->
        <!-- <span >{{indexNum}}</span> -->

        <span >
            {{msg}}
            <input type="button" value="删除" @click= "deleteChosen">
        </span>
        
        
        
    </div>
</template>

<script>
    export default {
        name:'listItem',
        props:{
            msg:{
                type:String,
            },
            indexNum:{
                type:Number,
            },
            doneData:{
                type:String,
            },
            indexDone:{
                type:Number,
            },
            flag:{
                type:Boolean,
            },
        },
        data(){
            return{
                
                
            }
        },
        methods:{
            deleteChosen(){
                
                this.$emit("deleteItem");
            },
            checkChange(){   
                // this.$emit("haveDone"); 
                this.$emit("checkChange");                
            },
            // deleteDoneChosen(){
            //     console.log("indexDone-->" + this.indexDone);
            //     this.$emit("deleteDoneChosen",this.indexDone);
            // },
            // doneCheckChange(){
            //     if(this.typeofCheck){
            //         console.log(this.indexDone + " " + this.doneData);
            //         this.$emit("cancelDone");
            //         console.log("触发完毕");
            //     }
            // },
        }
    }
</script>

<style scoped>

</style>