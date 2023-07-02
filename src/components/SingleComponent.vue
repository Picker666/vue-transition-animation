<template>
  <div>
    <div>
      <button v-on:click="show = !show">
        Toggle
      </button>
      <div class="transition">
        <transition name="fade">
          <p v-if="show">hello</p>
        </transition>
      </div>
    </div>

    <div>
    <button @click="show = !show">
      Toggle render
    </button>
    <div  class="transition">
      <transition name="slide-fade">
        <p v-if="show">hello</p>
      </transition>
    </div>
  </div>

  <div id="example-2">
    <button @click="show = !show">Toggle show</button>
    <div class="transition">
      <transition name="bounce">
        <p v-if="show">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris facilisis enim libero, at lacinia diam fermentum id. Pellentesque habitant morbi tristique senectus et netus.</p>
      </transition>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'singleComponent',
  data: function () {
    return {
      show: false,
    }
  }
}
</script>

<style scoped>
.transition {
  height: 58px;
  overflow: hidden;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}

.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>