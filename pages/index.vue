<template>
  <div>
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    <br />
    <button @click="mode = !mode" >change</button>
    <fade-transition class="container">
      <div v-if="mode"
        v-for="index in 30"
        :key="index"
        :data-index="index"
        class="color"
      />
    </fade-transition>
    <br />
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
    hola hola hola hola hola hola hola hola hola hola hola hola hola
  </div>
</template>

<script>
import FadeTransition from '~/transitions/FadeTransition'

export default {
  name: 'index',
  components: { FadeTransition },
  data () {
    return {
      mode: true
    }
  }
}
</script>

<style lang="scss" >
  .color {
    width: 1rem;
    height: 1rem;
    margin: 1rem;

    &:nth-child(10n+1) {
      background-color: lime;
    }
    &:nth-child(10n+2) {
      background-color: red;
    }
    &:nth-child(10n+3) {
      background-color: blue;
    }
    &:nth-child(10n+4) {
      background-color: pink;
    }
    &:nth-child(10n+5) {
      background-color: black;
    }
    &:nth-child(10n+6) {
      background-color: yellow;
    }
    &:nth-child(10n+7) {
      background-color: aqua;
    }
    &:nth-child(10n+8) {
      background-color: chocolate;
    }
    &:nth-child(10n+9) {
      background-color: lightcoral;
    }
    &:nth-child(10n+10) {
      background-color: olivedrab;
    }
  }

  .container {
    display: flex;
    flex-flow: row wrap;
    border-radius: 3px solid black;
  }
</style>
