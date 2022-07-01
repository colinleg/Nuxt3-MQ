<template>
  <div>
    <c1></c1>
  </div>
</template>

<script>
export default {
  inject: ["mq"],

  provide(){
    return {
      MQ: this.mq
    }
  },
  mounted(){
    // console.log(this.mq)
  }
}
</script>