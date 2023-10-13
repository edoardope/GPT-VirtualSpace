<script>
import {store} from '../store';

export default {
  name: "SetUpMenu",
  data() {
    return {
      store,
      worldDescription: "",
      worldName: "",
    }
  },
  methods: {
    submit(){
        let newWorld = {
            "name" : this.worldName,
            "description" : this.worldDescription
        }

        store.worlds.push(newWorld);

        store.currentScreen = "MainMenu";
    }
  }
}
</script>

<template>
  <div class="container-fluid">
    <div class="row justify-content-center">
      <div class="col-12 d-flex flex-column">
        <h1 class="mt-5 text-center">Virtual space setup</h1>
        <span class="mt-5 text-center text-white h2">Now you need to set up the virtual context for your character.</span><br>
        <span class="mt-5 text-center text-white">Give a detailed description of the enviroment and its dinamycs, <br> it can be very simple or very complex depending on what you want to create, <br> don't reference the character in this description focus only on the enviroment</span>
        <textarea v-model="this.worldDescription" class="mx-auto mt-3" name="" id="" cols="30" rows="10">
            put here the description of the virtual enviroment
        </textarea>
        <span class="mt-4 text-center text-white">Put here the name that you want to give to this enviroment</span>
        <input v-model="this.worldName" class="mx-auto mt-3" type="text" placeholder="Insert here the name">
        <button type="button" class="mx-auto btn btn-success mt-2" @click="submit()">Submit</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container-fluid{
  background-color: rgb(73, 69, 69);
  width: 100%;
  height: 100vh;

  textarea{
    width: 500px;
    border-radius: 10px;
  }

  input{
    width: 400px;
    background-color: transparent;
    border: 1px solid white;
    color: white;
    padding: 5px;
    border-radius: 5px;
  }
}
</style>
