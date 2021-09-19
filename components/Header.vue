<template>
  <v-toolbar
    :max-width="maxWidth"
    dense
    fixed
    height="90px"
    class="toobal-position"
    :color="bgColor"
    flat
    tile
  >
    <v-menu bottom left>
      <template #activator="{ on, attrs }">
        <v-btn class="d-flex d-md-none" dark icon v-bind="attrs" v-on="on">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>

      <v-list>
        <v-list-item>
          <v-btn
            v-for="social in socials"
            :key="social.name"
            icon
            :href="social.link"
          >
            <v-icon>mdi-{{ social.name }}</v-icon>
          </v-btn>
        </v-list-item>
        <v-list-item
          v-for="action in actionLinks"
          :key="action.name"
          :href="action.link"
        >
          <v-list-item-title> {{ action.name }} </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    <div class="pr-8 d-none d-md-flex">
      <v-btn
        v-for="social in socials"
        :key="social.name"
        :href="social.link"
        small
        icon
        target="_blank"
        color="white"
        ><v-icon>mdi-{{ social.name }}</v-icon></v-btn
      >
    </div>
    <div class="d-none d-md-flex">
      <v-btn color="white" text :href="actionLinks[0].link">
        {{ actionLinks[0].name }}</v-btn
      >
      <v-btn color="white" text :href="actionLinks[1].link">{{
        actionLinks[1].name
      }}</v-btn>
    </div>
    <v-spacer></v-spacer>
    <v-btn text color="rgba(0,0,0,0)">
      <v-toolbar-title
        ><v-img :src="headerLogo" :alt="headerAlt"
      /></v-toolbar-title>
    </v-btn>

    <v-spacer></v-spacer>
    <div class="d-none d-md-flex">
      <v-btn color="white" text :href="actionLinks[2].link">{{
        actionLinks[2].name
      }}</v-btn>
      <v-btn color="white" text :href="actionLinks[3].link">{{
        actionLinks[3].name
      }}</v-btn>
    </div>
    <div class="pl-8">
      <v-btn class="d-none d-md-flex" large outlined rounded color="white">
        My order <v-icon small class="pl-3">mdi-cart-outline</v-icon>
      </v-btn>
      <v-btn class="d-flex d-md-none" outlined rounded color="white">
        <v-icon small>mdi-cart-outline</v-icon>
      </v-btn>
    </div>
  </v-toolbar>
</template>

<script>
export default {
  name: 'Header',

  props: {
    socials: {
      type: Array,
      default: () => {},
    },
    actionLinks: {
      type: Array,
      default: () => {},
    },
    headerLogo: {
      type: String,
      default: '',
    },
    headerAlt: {
      type: String,
      default: '',
    },
  },

  data() {
    return {
      bgColor: 'rgba(255, 255, 255, 0)',
      maxWidth: '1300px',
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll(event) {
      this.bgColor = 'rgba(0, 0, 0, 0.6)'
      this.maxWidth = '100%'
      if (window.scrollY === 0) {
        this.bgColor = 'rgba(0, 0, 0, 0)'
        this.maxWidth = '1300px'
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.toobal-position {
  position: fixed;
  top: 0;
  z-index: 999;
  width: 100%;
}
::v-deep .v-toolbar__content {
  border-bottom: 1px solid rgba(255, 255, 255, 0.3);
}
</style>
