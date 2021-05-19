<template>
  <div id="app">
    <com-header v-bind:titleHeader="title" 
    v-on:changeTitleEven="changeTitles"
    />
    <list-user v-bind:listUser="listUser" />
      <p v-if="isActive == false" >Dao VIet Trung</p>
      <p v-if="isActive == true" >Devfast</p>
      <button v-on:click="conditionIf">submit</button>
  </div> 
</template>

<script>
import ComHeader from "./components/ComHeader.vue";
import ListUser from "./components/ListUser.vue";

export default {
  name: "app",
  data() {
    return {
      title: "test prop",
      listUser: [
        { id:100, email: "viettrung66@gmail.com", active: true },
        { id:101, email: "viettrung67@gmail.com", active: true },
        { id:102, email: "viettrung68@gmail.com", active: true },
      ],
      isActive : true,
    };
  },
  components: {
    ComHeader,
    ListUser,
    ListUser,
  },
  methods :{
    changeTitles(data){
      this.title = data.title;
    },
    conditionIf(){
      if(this.isActive){
        this.isActive = false;
      }
      else{
        this.isActive = true;
      }
    }
  }
};
</script>
