<template>
  <div class="frame">
    <div class="center">
      <div class="menu-icon" @click="start" :class="{'active': activeClass}">
        <div class="line-1 line" :class="{'no-animation': noAnimationClass}"></div>
        <div class="line-2 line" :class="{'no-animation': noAnimationClass}"></div>
        <div class="line-3 line" :class="{'no-animation': noAnimationClass}"></div>
        <div class="line-4 line" :class="{'no-animation': noAnimationClass}"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuButton',
  data () {
    return {
      activeClass: false,
      noAnimationClass: true
    }
  },
  methods: {
    start () {
      this.activeClass = !this.activeClass
      this.noAnimationClass = false
    }
  }
}
</script>

<style lang="scss">
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
  background: #e91e63;
  color: #fff;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

$menu-icon-line-height: 8px;
$menu-icon-line-space: 14px;
$menu-icon-line-offsetY: $menu-icon-line-height + $menu-icon-line-space;
$menu-icon-height: (3 * $menu-icon-line-height) + (2 * $menu-icon-line-space);
$cubic-bezier-in: cubic-bezier(0.3, 1, 0.7, 1);
$cubic-bezier-out: cubic-bezier(1, 0.7, 1, 0.3);

.menu-icon {
  width: 80px;
  height: $menu-icon-height;
  cursor: pointer;
  z-index: 50;

  .line {
    height: $menu-icon-line-height;
    width: 100%;
    background-color: #fff;
    border-radius: 3px;
    box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.3);
    transition: background-color 0.2s ease-in-out;
  }

  .line-1 {
    animation: animate-line-1-rev 0.7s ease-in-out;
  }
  .line-2 {
    margin: $menu-icon-line-space 0;
    animation: animate-line-2-rev 0.7s ease-in-out;
  }
  .line-3 {
    animation: animate-line-3-rev 0.7s ease-in-out;
  }

  .line-4 {
    margin-top: $menu-icon-line-space;
    animation: animate-line-4-rev 0.7s ease-in-out;
  }

  &:hover {
    .line {
      background-color: #fff;
    }
  }

  &.active {
    .line {
      background-color: #fff;
    }
    .line-1 {
      animation: animate-line-1 0.7s $cubic-bezier-in forwards;
    }
    .line-2 {
      animation: animate-line-2 0.7s $cubic-bezier-in forwards;
    }
    .line-3 {
      animation: animate-line-3 0.7s $cubic-bezier-in forwards;
    }

    .line-4 {
      animation: animate-line-4 0.7s $cubic-bezier-in forwards;
    }
  }
}

.no-animation {
  -webkit-animation: none !important;
  animation: none !important;
}

@keyframes animate-line-1 {
  0% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
  50% {
    transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(45deg);
  }
}
// shrinks and hides it
@keyframes animate-line-2 {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  100% {
    transform: scale(0);
    opacity: 0;
  }
}

@keyframes animate-line-3 {
  0% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
  50% {
    transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(135deg);
  }
}

@keyframes animate-line-4 {
  0% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
  50% {
    transform: translate3d(0, -$menu-icon-line-offsetY * 2, 0) rotate(0);
  }
  100% {
    transform: translate3d(
        $menu-icon-line-offsetY * 2,
        -$menu-icon-line-offsetY * 2,
        0
      )
      rotate(90deg);
  }
}

@keyframes animate-line-1-rev {
  0% {
    transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(45deg);
  }
  50% {
    transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
}
// grows and shows it
@keyframes animate-line-2-rev {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

@keyframes animate-line-3-rev {
  0% {
    transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(135deg);
  }
  50% {
    transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
}

@keyframes animate-line-4-rev {
  0% {
    transform: translate3d(
        $menu-icon-line-offsetY * 2,
        -$menu-icon-line-offsetY * 2,
        0
      )
      rotate(90deg);
  }
  50% {
    transform: translate3d(0, -$menu-icon-line-offsetY * 2, 0) rotate(0);
  }
  100% {
    transform: translate3d(0, 0, 0) rotate(0deg);
  }
}
</style>
