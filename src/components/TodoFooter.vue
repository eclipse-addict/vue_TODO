<template>
  <div>
    <span v-on:click="clearTodo">
     <i class="fa-sharp fa-solid fa-check-double"></i>
     Clear All
    </span>
  </div>
</template>

<script>
export default {
  methods: {
    clearTodo(){
      // this.$emit('clearAllItems')
      this.$store.commit('clearAll');
    }
  },
}
</script>

<style scoped>

</style>