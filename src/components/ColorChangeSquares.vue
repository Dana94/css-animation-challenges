<template>
  <div class="frame">
    <div class="container">
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
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 2px;
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  background: #1ebae9;
  color: #fff;

  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  width: 150px;
  height: 150px;
  border: 1px solid;
  position: relative;
}

.square {
  width: 50px;
  height: 50px;
  background-color: #ffffff;

}

.square-1 {
    position: absolute;
    left: 0;
    top: 0;
    animation: square1 0.7s forwards;
  }

  .square-2 {
    position: absolute;
    right: 0;
    bottom: 0;
    animation: square2 0.7s forwards;

  }

@keyframes square1 {
  0% {
    left: 0px;
  }
  50% {
    left: 50px;
  }
  100% {
    left: 100px;
  }
}

@keyframes square2 {
  0% {
    right: 0px;
  }
  50% {
    right: 50px;
  }
  100% {
    right: 100px;
  }
}
</style>
