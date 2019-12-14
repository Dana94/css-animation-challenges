<template>
  <div class="frame container">
    <div class="center">
      <h1 class="header">
        I'm
        <br>
        <span class="word-wrapper">
          <b :class="{'is-visible': word === 1, 'is-hidden': word !== 1}">Strong</b>
          <b :class="{'is-visible': word === 2, 'is-hidden': word !== 2}">Smart</b>
          <b :class="{'is-visible': word === 3, 'is-hidden': word !== 3}">Determined</b>
          <b :class="{'is-visible': word === 4, 'is-hidden': word !== 4}">Brave</b>
          <b :class="{'is-visible': word === 5, 'is-hidden': word !== 5}">Georgeous</b>
        </span>
      </h1>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      word: 1
    }
  },
  created () {
    setInterval(() => {
      switch (this.word) {
        case 1:
          this.word = 2
          break
        case 2:
          this.word = 3
          break
        case 3:
          this.word = 4
          break
        case 4:
          this.word = 5
          break
        case 5:
          this.word = 1
          break
      }
    }, 2000)
  }
}
</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Raleway&display=swap');
@import '../assets/styles.scss';

.container {
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  background: #e91e63;
  color: #fff;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.word-wrapper {
  overflow: hidden;
  position: relative;
  vertical-align: bottom;
  text-align: left;
  width: auto;
  padding: 0;
  display: inline-block;
  border-bottom: 3px solid yellow;
}

.word-wrapper b {
  display: inline-block;
  position: absolute;
  white-space: nowrap;
  left: 0;
  width: auto !important;
  opacity: 0;
  top: .2rem;
}

.is-hidden {
  animation: slide-out 0.6s;
}

.is-visible {
  top: 0 !important;
  opacity: 1 !important;
  animation: slide-in 0.6s;
  position: relative !important;
}

@keyframes slide-in {
  0% {
    opacity: 0;
    transform: translateY(-100%);
  }
  60% {
    opacity: 1;
    transform: translateY(20%);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slide-out {
  0% {
    opacity: 1;
    transform: translateY(0);
  }
  60% {
    opacity: 0;
    transform: translateY(120%);
  }
  100% {
    opacity: 0;
    transform: translateY(100%);
  }
}

.header {
  font-family: 'Raleway', sans-serif;
  letter-spacing: .2rem;
  width: 9rem;
}

</style>
