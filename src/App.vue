<script setup>
import First from '../src/components/First.vue'
import Second from '../src/components/Second.vue'
import Third from '../src/components/Third.vue'
import { ref } from 'vue'
// const components = [
//   {title: false, indez: 0},
//   {title: false, indez: 1}, 
//   {title: false, indez: 2}
// ]
// const show = ref(false)
const activeComponent = ref("")
// const active = ref(false)
// function revial(index) {
//   // activeComponent.value = components[index].component
//   active.value = !components[index].title
// }
// function revial(index) {
//   const component = components[index]
//   if (component) {
//     component.title = !component.title
//   }
// }

</script>

<template>
  <div class="app">
    <div class="container">
      <div class="total">
        <div class="first">
          <div class="info">
            <div class="li">
              <div> lorem 1</div>
              <!-- <div @click="revial(0)" class="plus">+</div> -->
              <div @click="activeComponent = 'first'" class="plus">+</div>
            </div>
            <hr>
            <div class="component">
              <!-- <First v-show="components[0].title" /> -->
              <First v-show="activeComponent === 'first'" /> 
            </div>
          </div>
        </div>
        <div class="two">
          <div class="info">
            <div class="li">
              <div>lorem 2</div>
              <div @click="activeComponent = 'second'" class="plus">+</div>
              
            </div>
            <hr>
            <div class="component">
              <Second  v-show="activeComponent === 'second'" />
            </div>
          </div> 
        </div>
        <div class="tree">
          <div class="info">
            <div class="li">
              <div>lorem 3</div>
              <div @click="activeComponent = 'third'" class="plus">+</div>
            </div>
            <hr>
            <div class="component">
              <Third v-show="activeComponent === 'third'" />
            </div>
          </div> 
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.app{
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  max-width: 100vw;
}
.container {
  display: flex;
  align-items: center;
  justify-content: center;
}
.total {
  display: flex;
  flex-direction: column;
  width: 800px;
  height: 500px;
  background-color: #789c6a
}
.info {
  margin: 20px 40px;
  display: flex;
  flex-direction: column;
  background-color: #91b7c9;
}
.li{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.plus{
  padding: 10px;
  margin: 10px;
  font-size: 25px;
  border: 2px solid black;
  cursor: pointer;
}
</style>