<template>
  <div class="frame">
    <div class="container">
      <div class="square square-1">
        <!-- <div class="side1"></div>
        <div class="side2"></div> -->
      </div>
      <div class="square square-2">
        <div class="side1"></div>
        <div class="side2"></div>
      </div>
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
  animation: 0.7s linear 0s infinite alternate square1;
  display: flex;

  .side1 {
    width: 50%;
    animation: 0.7s linear 0s infinite alternate square1side1;
  }
  .side2 {
    width: 50%;
    animation: 0.7s linear 0s infinite alternate square1side2;
  }
}

.square-2 {
  position: absolute;
  right: 0;
  bottom: 0;
  animation: square2 0.7s alternate;
  display: flex;

  .side1 {
    width: 50%;
    animation: square2side1 0.5s alternate;
  }

  .side2 {
    width: 50%;
    animation: square2side2 0.5s alternate;
  }
}

@keyframes square1 {
  0% {
    left: 0px;
    background: linear-gradient(90deg, #ffffff, #5c5c5c);

  }
  50% {
    left: 50px;
    background: linear-gradient(90deg, #ffffff, #5c5c5c,#000000);

  }
  100% {
    left: 100px;
    background-color: #000000;

  }
}

@keyframes square1side1 {
  0% {
    background-color: #ffffff;
  }
  // 50% {
  //   background-color: linear-gradient(90deg, #ffffff, #000000);
  // }
  100% {
    background-color: #000000;
  }
}

@keyframes square1side2 {
  0% {
    background-color: #ffffff;
  }
  // 50% {
  //   background-color: linear-gradient(90deg, #ffffff, #000000);
  // }
  100% {
    background-color: #000000;
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

@keyframes square2side1 {
  0% {
    background-color: #ffffff;
  }
  100% {
    background-color: #000000;
  }
}

@keyframes square2side2 {
  0% {
    background-color: #ffffff;
  }
  50% {
    background-color: #ffffff;
  }
  100% {
    background-color: #000000;
  }
}
</style>
