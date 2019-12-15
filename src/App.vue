<template>
  <div id="app">
    <MenuButton/>
    <ColorChangeSquares/>
    <WordScroll/>
  </div>
</template>

<script>
import MenuButton from './components/MenuButton.vue'
import ColorChangeSquares from './components/ColorChangeSquares.vue'
import WordScroll from './components/WordScroll.vue'

export default {
  name: 'app',
  components: {
    MenuButton,
    ColorChangeSquares,
    WordScroll
  }
}
</script>

<style lang="scss">
#app {
  display: grid;
  grid-template-columns: 1fr;

  @media (min-width: 768px) {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>
