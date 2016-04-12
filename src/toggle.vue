// out: ..
<template lang="jade">
button(@click="toggle | notPrevented | prevent",:class="[isOn ? onClass : offClass]")
  slot
  slot(name="on" v-if="isOn")
  slot(name="off" v-else)
</template>

<script lang="coffee">
module.exports =

  filters:
     notPrevented: require("vue-filters/notPrevented")
     prevent: require("vue-filters/prevent")

  props:
    onClass:
      type: String
      default: "on"
    offClass:
      type: String
      default: "off"
    isOn:
      type: Boolean
      default: false

  methods:
    toggle: ->
      if @isOn
        @$emit("off")
      else
        @$emit("on")
      @$emit("toggle")
      @isOn = !@isOn

</script>
