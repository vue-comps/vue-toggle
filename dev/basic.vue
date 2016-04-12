<template lang="jade">
.container
  a(href="https://github.com/vue-comps/vue-parallax/blob/master/dev/basic.vue") source
  toggle(:is-on.sync="isOn") click to switch
    span(slot="on")  off
    span(slot="off")  on
  span  isOn: {{isOn}}
</template>

<script lang="coffee">
module.exports =
  data: ->
    isOn: false
  components:
    "toggle": require "../src/toggle.vue"
</script>

<style lang="stylus">
.container > a
  position absolute
  left 250px
  top 40px
</style>
