<template>
  <div>
    <div id="Block" class="Block"></div>
    <div id="Cursor" class="Cursor"></div>
    <nuxt/>
  </div>
</template>

<script>
// Viewport
var viewportWidth
var viewportHeight
var viewportDim
var viewportDevice
var dotWidth
var sectionHeight

export default {
  methods: {

  },
  mounted: function () {
    var Block = document.getElementById('Block')
    setTimeout(function(){
      Block.classList.add('fade-out')
      setTimeout(function(){
        Block.remove()
      }, 500)
    }, 200)
  },
}
</script>

<style>
html {
  font-family: "Noto Sans", sans-serif;
  font-size: 16px;
  word-spacing: 0px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  width: 100%;
}

::selection {
  background: rgba(128,128,128,0.3);
}
::-moz-selection {
  background: rgba(128,128,128,0.3);
}

body {
  width: 100%;
  background: #ffffff;
  font-size: 1.5vw;
  line-height: 1.25;
  font-weight: normal !important;
  font-display: swap;

  @media (max-width: 666px) {
    font-size: 4.1vw;
    line-height: 1.5;
    letter-spacing: 0.02em;
  }

}

body p {
  @media (max-width: 666px) {
    margin-bottom: 4.5vw;
  }
}

.Block {
  position: fixed;
  z-index: 9999;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #000;
  transition: all 0.4s ease;
}

.Block.fade-out {
opacity: 0;
}

p {
  margin-bottom: 1.95vw;
}

a {
  color: #fff;
  text-decoration: none;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}
</style>
