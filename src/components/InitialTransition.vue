<template>
  <div>
    <transition
      appear
      appear-class="initial-appear"
      appear-to-class="initial-appear-to"
      appear-active-class="initial-appear-active"
    >
      <div>6666</div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'initialTransition',
  data: function () {
    return {

    }
  }
}
</script>

<style scoped>
  .initial-appear {
    opacity: 0;
    font-size: 16px;
  }
  .initial-appear-to {
    opacity: 0.1;
    font-size: 26px;
  }
  .initial-appear-active{
    transition: opacity fontSize 6 ease;
  }
</style>