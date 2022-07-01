<template>
    <div>
    <!--
        mq is {{ mq }}
        isMobile is {{ isMobile }}
    -->

        <div v-show="isMobile" class="mobile"> Texte mobile</div>
        <div v-show="!isMobile" class="desktop"> Desktop</div>

    </div>
</template>

<script>
export default {
  watch: {
  },
  methods: {
  },
  props: {
  },
    // Le "provide est dans app.vue"
    inject: ["MQ"],

    computed: {
        mq(){
            return this.MQ.current
        },

        isMobile() {
            if( this.MQ.current == "xs" || this.MQ.current == "sm" || this.MQ.current == "md"){
                return true
            } else {
                return false
            }
        }
    },

}
</script>

<style scoped>
.mobile{
    color: white;
    width: 100vw;
    height: 2rem;
    background-color: red;
}

.desktop{
    color: white;
    width: 50vw;
    height: 2rem;
    background-color: blue;
}
</style>