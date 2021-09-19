<template>
  <v-card color="white">
    <v-img width="100%" cover height="500px" :src="bgImage" />
  </v-card>
</template>

<script>
export default {
  name: 'CardImage',

  props: {
    bgImage: {
      type: String,
      default: '',
    },
  },
}
</script>

<style lang="scss" scoped></style>
