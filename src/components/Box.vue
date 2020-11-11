<template>
  <div class="box col-4 p-2">
    <div class="border border-warning shadow">
      this is a box
      <button class="btn btn-info" @click="state.things.push('a thing')">
        add thing
      </button>
      <button class="btn btn-danger" @click="state.things.pop()">
        remove thing
      </button>
      <transition-group name="custom" tag="ul">
        <li v-for="thing in state.things" :key="thing">
          {{ thing }}
        </li>
      </transition-group>
    </div>
  </div>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'Box',
  setup() {
    const state = reactive({
      things: []
    })
    return { state }
  }
}
</script>

<style scoped>

</style>
