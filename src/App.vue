<template>
  <div id="app">
    
    <entryData @submitData="handleReceiverData"/>
    <!-- <span>{{doingList}}</span> -->
    <doing :entryMsg = doingList @sendBackDoneList = "handleDoneList"/>
    <done :doneMsg = doneList :doingList=doingList />
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import entryData from './components/entryData.vue'
import doing from './components/doing.vue'
import done from './components/done.vue'

export default {
  name: 'app',
  components: {
    entryData,
    doing,
    done,
  },
  data(){
    return{
      receiverData:"",
      doingList:[],
      doneList:[],
    }
  },
  methods:{
    handleReceiverData(values){
      
      // alert(this.doingList);
      this.doingList.push(values);
      // alert(this.doingList);
    },
    handleDoneList(values){
      // alert("收到doing返回的doneList--" + values);
      this.doneList = values;
      console.log("收到doing返回的doneList--" + this.doneList);
    }
  },

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
