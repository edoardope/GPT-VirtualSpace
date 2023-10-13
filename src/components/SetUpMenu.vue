<script>
import {store} from '../store';

export default {
  name: "SetUpMenu",
  data() {
    return {
      store,
      key: "",
      alert: "d-none"
    }
  },
  methods: {
    submit(){
      if(!this.key == ""){
        store.key = this.key
        store.currentScreen = "MainMenu"
      } else {
        this.alert = "d-block"
      }
    }
  }
}
</script>

<template>
  <div class="container-fluid">
    <div class="row justify-content-center">
      <div class="col-12 d-flex flex-column">
        <h1 class="mt-5 text-center">Welcome to GPT-VirtualSpace</h1>
        <span class="mt-5 text-center">To start you need to insert an openAi api key</span>
        <input class="mx-auto mt-3" type="text" placeholder="Insert here your key" v-model="this.key">
        <button type="button" class="mx-auto btn btn-success mt-2" @click="submit()">Submit</button>
        <div :class="this.alert" class="alert alert-danger mt-5 mx-auto text-center" role="alert">
          Key missing
        </div>
      </div>
    </div>

  </div>
</template>

<style lang="scss" scoped>
.container-fluid{
  background-color: rgb(73, 69, 69);
  width: 100%;
  height: 100vh;

  h1{
    font-size: 500%;
  }

  span{
    color: white;
    font-size: 200%;
  }

  input{
    width: 400px;
    background-color: transparent;
    border: 1px solid white;
    color: white;
    padding: 5px;
    border-radius: 5px;
  }

  button{
    width: 100px;
  }

  .alert{
    width: 200px;
  }
}
</style>
