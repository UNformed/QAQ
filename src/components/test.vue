<template>
  <div>
    <div class="btn">aaaaaa</div>
    <div class="bg-dot-rand black-theme animate2"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      d: ""
    };
  }
};
</script>
<style lang='less' scoped>
.btn {
  outline: none;
  border: none;
  z-index: 1;
  position: relative;
  color: white;
  background-color: #40a9ff;
  padding: 0.5em 1em;
}
.btn:hover {
  cursor: pointer;
}
.btn::before {
  content: "";
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  //background-color: #fa541c;
  position: absolute;
  border: 2px solid #40a9ff;
  z-index: -1;
  transform: scaleY(1);
}
.btn:hover::before {
  transition: all 0.4s ease-in-out;
  transform: scaleY(1.5);
  opacity: 0;
}
.bg-dot-rand {
  margin-top: 20px;
  width: 200px;
  height: 200px;
  background-color: #eee;
  background-image: radial-gradient(circle, #fb3 5px, transparent 0),
    radial-gradient(circle, #ab4 13px, transparent 0),
    radial-gradient(circle, #655 31px, transparent 0);
  background-repeat: no-repeat;
  background-size: 101px 203px, 147px 60px, 373px 201px;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.4);
}
.animate1 {
  animation: move 4s linear infinite;
}
.animate2 {
  animation: move2 4s linear infinite;
}
@keyframes move {
  0% {
    background-position: 0 0, 0 0, 0 0;
  }
  50% {
    background-position: -10px 0, 20px 0, 30px 0;
  }
  100% {
    background-position: 0 0, 30px 0, 10px 0;
  }
}
@keyframes move2 {
  0% {
    background-position: 0 0, 0 0, 0 0;
  }
  50% {
    background-position: -10px 30px, 20px 0, -40px 80px;
  }
  100% {
    background-position: 0 20px, 60px -20px, 10px 30px;
  }
}
</style>