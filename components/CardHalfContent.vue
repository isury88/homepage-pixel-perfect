<template>
  <v-card color="white" height="100%" class="pl-7">
    <v-card-text style="height: 100%">
      <div
        class="d-flex flex-column align-start justify-center"
        style="height: 100%; max-width: 579px"
      >
        <p class="primary--text text-left overline ma-0 text-uppercase">
          {{ about.overline }}
        </p>
        <h1 class="black--text display-2 text-left font-weight-bold mb-7">
          {{ about.title }}
        </h1>
        <p class="black--text text-left ma-0">
          {{ about.content }}
        </p>
        <v-btn
          depressed
          class="mt-5 white--text px-12"
          dark
          color="primary"
          rounded
          x-large
          size="15px"
          :href="about.btnLink"
          >{{ about.btnText }}</v-btn
        >
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'CardHalfContent',

  props: {
    about: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style lang="scss" scoped></style>
