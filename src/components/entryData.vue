<template>
    <div id="inputData">
        <span style="padding-right:30px">toDoList</span>
        <form >
            <input v-model="entryData" type="text" placeholder="添加toDo" >
            <input type="button" value="submit" @click="handleSubmit">
        </form>
        <!-- <span>entryData:{{entryData}}</span> -->
    </div>
</template>

<script>
    export default {
        name:'inputData',
        data(){
            return{
               
                entryData:"",
            }
        },methods:{
            handleSubmit(){
                this.$emit("submitData",this.entryData);
            },
        },
        
    }
</script>

<style>
#title {
    text-align: center;

}
</style>
