<template>
  <div class="home flex-grow-1 d-flex flex-column align-items-center justify-content-center">
    <img src="https://bcw.blob.core.windows.net/public/img/8600856373152463" alt="CodeWorks Logo">
    <div class="col-6">
      <button class="btn btn-info" @click="state.bool = !state.bool">
        show/hide
      </button>
      <transition name="fade">
        <img v-show="state.bool" src="https://v3.vuejs.org/images/transitions.svg" alt="">
      </transition>
    </div>
  </div>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'Home',
  setup() {
    const state = reactive({
      bool: true
    })
    return { state }
  }
}
</script>

<style scoped lang="scss">
.home{
  text-align: center;
  user-select: none;
  > img{
    height: 200px;
    width: 200px;
  }
}
</style>
