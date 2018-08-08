<template>
    <li @click="handdelet">{{content}}</li>

</template>

<script>
export default {
  props:['content','index'],
  methods:{
      handdelet(){
        this.$emit('delete',this.index)
      }
  }
}
</script>

<style scoped>

</style>
