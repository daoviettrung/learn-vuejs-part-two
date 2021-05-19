<template>
  <div id="app">
    <com-header
      v-bind:titleHeader="title"
      v-on:changeTitleEven="changeTitles"
    />

    <list-user v-bind:listUser="listUser" />

    <p v-if="isActive == false">Dao VIet Trung</p>
    <p v-if="isActive == true">Devfast</p>
    <button v-on:click="conditionIf">submit</button>

    <div class="example ex1">
      <h4>Select Color</h4>
      <label class="radio red">
        <input type="radio" name="group1" />
        <span>Red</span>
      </label>
      <label class="radio blue">
        <input type="radio" name="group1" />
        <span>Blue</span>
      </label>
      <label class="radio orange">
        <input type="radio" name="group1" />
        <span>Orange</span>
      </label>
    </div>

    <input type="checkbox" id="trung1" value="trung1" v-model="checkedNames" />
    <label for="trung1">trung1</label>
    <input type="checkbox" id="trung2" value="trung2" v-model="checkedNames" />
    <label for="trung2">trung2</label>
    <input type="checkbox" id="trung3" value="trung3" v-model="checkedNames" />
    <label for="trung3">trung3</label>
    <br />
    <span>Checked names: {{ checkedNames }}</span>

     <h1 class="#">{{ name | strUpperCase | lastFil}}</h1>

     
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
        { id: 100, email: "viettrung66@gmail.com", active: true },
        { id: 101, email: "viettrung67@gmail.com", active: true },
        { id: 102, email: "viettrung68@gmail.com", active: true },
      ],
      isActive: true,
      dataStyle: " color: green",
      checkedNames: [],
      name: "Dao Viet Trung",
    };
  },
  components: {
    ComHeader,
    ListUser,
    ListUser,
  },
  methods: {
    changeTitles(data) {
      this.title = data.title;
    },
    conditionIf() {
      if (this.isActive) {
        this.isActive = false;
      } else {
        this.isActive = true;
      }
    },
  },
  filters: {
    strUpperCase: function (data) {
      return data.toUpperCase();
    },
    lastFil: function (data) {
      return data.bold();
    },
  },
};
</script>
<style>
.example {
  margin: 20px;
}
.example input {
  display: none;
}
.example label {
  margin-right: 20px;
  display: inline-block;
  cursor: pointer;
}

.ex1 span {
  display: block;
  padding: 5px 10px 5px 25px;
  border: 2px solid #ddd;
  border-radius: 5px;
  position: relative;
  transition: all 0.25s linear;
}
.ex1 span:before {
  content: "";
  position: absolute;
  left: 5px;
  top: 50%;
  -webkit-transform: translatey(-50%);
  transform: translatey(-50%);
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background-color: #ddd;
  transition: all 0.25s linear;
}
.ex1 input:checked + span {
  background-color: #fff;
  box-shadow: 0 0 5px 2px rgba(0, 0, 0, 0.1);
}
.ex1 .red input:checked + span {
  color: red;
  border-color: red;
}
.ex1 .red input:checked + span:before {
  background-color: red;
}
.ex1 .blue input:checked + span {
  color: blue;
  border-color: blue;
}
.ex1 .blue input:checked + span:before {
  background-color: blue;
}
.ex1 .orange input:checked + span {
  color: orange;
  border-color: orange;
}
.ex1 .orange input:checked + span:before {
  background-color: orange;
}
</style>
