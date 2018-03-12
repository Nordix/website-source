<template>
  <section class="container">
    <div>
      <SectionOne/>
      <SectionTwo/>
      <FooterOne/>
    </div>
  </section>
</template>

<script>
import SectionOne from '~/components/SectionOne.vue'
import SectionTwo from '~/components/SectionTwo.vue'
import FooterOne from '~/components/FooterOne.vue'

export default {
  components: {
    SectionOne,
    SectionTwo,
    FooterOne
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  width: 100%;

  &:hover {
    cursor: none !important;
  }

  @media (max-width: 666px) {
    cursor: auto !important;
  }
}
</style>
