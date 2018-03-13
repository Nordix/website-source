<template>
  <div id="Footer" class="Footer">
    Copyright (C) 2018, Nordix Foundation | Licensed under <a href="https://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>
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
    checkViewport () {
      if (viewportWidth < 667) {
        viewportDevice = 'mobile'
        dotWidth = Math.floor(viewportWidth / 8)
      } else {
        dotWidth = Math.floor(viewportWidth / 24)
        viewportDevice = 'desktop'
        sectionHeight = dotWidth*30
      }
      document.querySelector('body').classList.remove('viewport-device-desktop', 'viewport-device-tablet', 'viewport-device-mobile')
      document.querySelector('body').classList.add('viewport-device-' + viewportDevice)
      if (viewportDim > 2) {
        document.querySelector('body').classList.remove('viewport-dim-square', 'viewport-dim-landscape')
        document.querySelector('body').classList.add('viewport-dim-landscape')
      } else {
        document.querySelector('body').classList.remove('viewport-dim-square', 'viewport-dim-landscape')
        document.querySelector('body').classList.add('viewport-dim-square')
      }
    },
    resizeLogic () {
      viewportWidth = window.innerWidth
      viewportHeight = window.innerHeight
      viewportDim = viewportWidth / viewportHeight
      this.checkViewport()

      var section = document.getElementById('Footer');

      if (viewportDevice == 'mobile') {
        section.style.padding = (dotWidth*0.5)+'px'
        section.style.paddingTop = (dotWidth*0.5)+'px'
        section.style.paddingBottom = (dotWidth*0.5)+'px'
      } else {
        section.style.padding = (dotWidth*1)+'px'
        section.style.paddingTop = (dotWidth*0.25)+'px'
        section.style.paddingBottom = (dotWidth*0.25)+'px'
      }

    },
  },
  mounted: function () {
    this.resizeLogic()
    // RESIZE
    window.addEventListener('resize', this.resizeLogic)
  },
}
</script>

<style>
.Footer {
  width: 100%;
  float: left;
  font-size: 10px;
  line-height: 10px;
  //font-size: 1.2vw;
  //line-height: 1.25;
  background: #4ddb84;
  //background: #aaa;
  color: #fff;
  color: #000;

  @media (max-width: 666px) {
    font-size: 4.1vw;
    line-height: 1.5;
    letter-spacing: 0.02em;
  }

}
</style>
