<template>
    <div class="main">
      <div class="slide"
           :style="{'left': left}"
           @touchstart="touchStartHandle"
           @touchmove="touchMoveHandle"
           @touchend="TouchEndHandle">
      </div>
      <h3>test</h3>
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
            console.log('has add')
        },
        addOne() {
          console.log(12)
        },
        addTwo() {
          console.log(22)
          console.log('lalala')
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
