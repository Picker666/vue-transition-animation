<template>
  <div>
    <transition>
      <button v-if="isEditing" key="save" @click="handleClick">
        on
      </button>
      <button v-else key="edit" @click="handleClick">
        off
      </button>
    </transition>
    <br>
    <div class="position">
      <transition>
        <button v-if="isEditing" key="save" @click="handleClick">
          on
        </button>
        <button v-else key="edit" @click="handleClick">
          off
        </button>
      </transition>
    </div>

    <div class="position1">
      <transition name="fade" mode="out-in">
        <button key="save" v-if="isEditing" @click="handleClick">
          on
        </button>
        <button v-else key="edit" @click="handleClick">
          off
        </button>
      </transition>
    </div>

    <div :style="{overflow: 'hidden', textAlign: 'left'}">
      <transition name="fade1" mode="in-out">
        <button key="save" v-if="isEditing" @click="handleClick">
          on
        </button>
        <button v-else key="edit" @click="handleClick">
          off
        </button>
      </transition>
    </div>

  <hr>
  </div>
</template>

<script>
export default {
  name: 'MultiElementTransition',
  data: function () {
    return {
      isEditing: true
    }
  },
  methods: {
    handleClick() {
      this.isEditing = !this.isEditing;
    },
  }
}
</script>

<style scoped>
  .position, .position1 {
    position: relative;
    height: 22px;
  }

  .position button {
    left: 0;
    position: absolute;
  }

  .position1 {
    text-align:left;
  }

.fade-enter-active {
  transition: all 1s ease;
}
.fade-leave-active {
  transition: all 1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.fade-enter {
  opacity: 0;
}

.fade-leave-to {
  opacity: 0;
}

.fade1-leave-active {
  transition: all 1s ease;
}
.fade1-enter-active {
  transition: all 1s ease;
}
.fade1-enter-to {
  transform: translateX(-31px);
  /* opacity: 1; */
  position: absolute;
  z-index: 99;
}
.fade1-leave-to {
  transform: translateX(-31px);
  /* opacity: 0; */
  position: absolute;
  z-index: 9;
}
</style>