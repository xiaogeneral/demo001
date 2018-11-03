<template>
    <div class="main">
      <div class="slide"
           :style="{'left': left}"
           @touchstart="touchStartHandle"
           @touchmove="touchMoveHandle"
           @touchend="TouchEndHandle">
      </div>
      <h3>testhahaha</h3>
    </div>
</template>

<script>
    export default {
      name: "test001",
      data() {
        return {
          left: 0
        }
      },
      methods: {
        touchStartHandle(e) {
          const point = e.touches[0];
          this.pointX = point.pageX;
          this.distX = 0;
          console.log('start', this.pointX)
        },
        touchMoveHandle(e) {
          console.log('-----', e);
          e.preventDefault();
          const point = e.touches[0];
          let deltaX = point.pageX - this.pointX;
          this.left = deltaX + 'px';
          // this.pointX = point.pageX;
          console.log('move', this.pointX)
        },
        TouchEndHandle() {

        },
        addOne() {
          console.log(12)
          console.log('lalala')
        },
        addTwo() {
          console.log(22)
        }
      }
    }
</script>

<style scoped>
  .slide {
    position: absolute;
    width: 100px;
    height: 60px;
    background-color: cadetblue;
  }
</style>
