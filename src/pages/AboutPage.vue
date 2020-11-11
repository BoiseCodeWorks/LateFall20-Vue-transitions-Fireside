<template>
  <div class="about container-fluid pl-3">
    <h1>This is the about page</h1>
    <button class="btn btn-info" @click="state.boxes.push('box')">
      add box
    </button>
    <button class="btn btn-danger" @click="state.boxes.pop()">
      remove box
    </button>
    <transition-group name="fade" tag="div" class="row">
      <Box v-for="box in state.boxes" :key="box">
      </Box>
    </transition-group>
  </div>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'About',
  setup() {
    const state = reactive({
      boxes: []
    })
    return { state }
  }
}
</script>

<style scoped>

</style>
