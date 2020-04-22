<template>
  <main>
    <section class="section__top">
      <div class="section__image">
        <v-img :src="sectionImage.url" :alt="sectionImage.alt" />
      </div>
      <div class="section_cal"></div>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      sectionImage: {
        url: 'man-holding-black-dumbbell.jpg',
        alt: 'man-holding-black-dumbbell'
      }
    };
  }
};
</script>
