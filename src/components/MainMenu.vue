<script>
import {store} from '../store';

export default {
  name: "MainMenu",
  data() {
    return {
      store,
    }
  },
  methods: {
    CreateWorld(){
        store.currentScreen = "WorldSetUp"
    }
  }
}
</script>

<template>
  <div class="container-fluid">
    <div class="row justify-content-center">
      <div class="col-12 d-flex flex-column">
        <h1 class="mt-5 text-center">Main menu</h1>
        <span class="mt-5 text-center text-white h3">Select one option:</span><br>
        <button type="button" class="mx-auto btn btn-success mt-2" @click="CreateWorld()">Create enviroment</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container-fluid{
  background-color: rgb(73, 69, 69);
  width: 100%;
  height: 100vh;

}
</style>