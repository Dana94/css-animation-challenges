<template>
  <div class="frame container">
    <div class="center">
      <div class="square square-1"></div>
      <div class="square square-2"></div>
    </div>
  </div>
</template>
<script>
export default {

}
</script>
<style lang="scss" scoped>
@import '../assets/styles.scss';

.container {
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  background: #1ebae9;
  color: #fff;

  display: flex;
  align-items: center;
  justify-content: center;
}

.center {
  width: 150px;
  height: 150px;
  position: relative;
}

.square {
  width: 50px;
  height: 50px;
}

.square-1 {
  position: absolute;
  left: 0;
  top: 0;
  background-color: #ffffff;
  animation: 4s linear 0s infinite square1;
}

.square-2 {
  position: absolute;
  right: 0;
  bottom: 0;
  background-color: #ffffff;
  animation: 4s linear 0s infinite square2;
}

@keyframes square1 {
  0% {
    left: 0;
    top: 0;
    background-color: #ffffff;
  }
  25% {
    left: 100px;
    top: 0;
    background-color: #000000;
  }
  50% {
    left: 100px;
    top: 100px;
    background-color: #ffffff;
  }
  75% {
    left: 0px;
    top: 100px;
    background-color: #000000;
  }
  100% {
    left: 0;
    top: 0;
    background-color: #ffffff;
  }
}

@keyframes square2 {
  0% {
    right: 0;
    bottom: 0;
    background-color: #ffffff;
  }
  25% {
    right: 100px;
    bottom: 0;
    background-color: #000000;
  }
  50% {
    right: 100px;
    bottom: 100px;
    background-color: #ffffff;
  }
  75% {
    right: 0;
    bottom: 100px;
    background-color: #000000;
  }
  100% {
    right: 0;
    bottom: 0;
    background-color: #ffffff;
  }
}
</style>
