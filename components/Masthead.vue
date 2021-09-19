<template>
  <v-container fluid class="pa-0 d-flex flex-direction-column justify-center">
    <slot />
    <v-carousel
      :show-arrows="false"
      height="900px"
      :hide-delimiter-background="true"
      delimiter-icon="mdi-minus"
    >
      <v-carousel-item
        v-for="(item, i) in items"
        :key="i"
        cover
        :src="require('~/assets/images/masthead.jpg')"
      >
        <div
          class="d-flex flex-column align-center justify-center mx-auto"
          style="height: 100%; max-width: 686px"
        >
          <p class="white--text text-center overline ma-0 text-uppercase">
            {{ pretitle }}
          </p>
          <h1 class="white--text display-2 text-center font-weight-bold">
            {{ title }}
          </h1>
          <v-btn
            depressed
            class="mt-5 white--text px-12"
            dark
            color="primary"
            rounded
            x-large
            size="15px"
            :href="cta.link"
            >{{ cta.text }}</v-btn
          >
        </div>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>
<script>
export default {
  name: 'Masthead',

  props: {
    pretitle: {
      type: String,
      default: '',
    },
    title: {
      type: String,
      default: '',
    },
    cta: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      items: [
        {
          src: '_nuxt/assets/images/masthead.jpg',
        },
        {
          src: '_nuxt/assets/images/masthead.jpg',
        },
        {
          src: '_nuxt/assets/images/masthead.jpg',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
::v-deep .v-carousel .v-btn--active .v-btn__content .v-icon {
  color: #d4b254;
  opacity: 1;
}
::v-deep .v-carousel .v-btn {
  margin-right: 20px;
}
::v-deep .mdi-minus::before {
  font-size: 80px;
}
::v-deep .theme--dark.v-btn--active::before {
  opacity: 0;
}
</style>
