<template>
  <div>
    <Masthead :pretitle="pretitle" :title="title" :cta="cta">
      <Header
        :header-logo="require('~/assets/images/logo.png')"
        header-alt="Kitchen Design Logo"
        :socials="socials"
        :action-links="actionLinks"
      />
    </Masthead>
    <v-row class="ma-0">
      <v-col cols="12" md="6" class="pa-0 d-none d-md-block">
        <CardImage :bg-image="require('~/assets/images/interior.jpg')" />
      </v-col>
      <v-col cols="12" md="6" class="pa-0">
        <CardHalfContent :about="about" />
      </v-col>
    </v-row>
  </div>
</template>
<script>
import Header from '@/components/Header.vue'
import Masthead from '@/components/Masthead.vue'
import CardImage from '@/components/CardImage.vue'
import CardHalfContent from '@/components/CardHalfContent.vue'

export default {
  components: {
    Header,
    Masthead,
    CardImage,
    CardHalfContent,
  },
  data() {
    return {
      socials: [
        { name: 'facebook', link: 'https://facebook.com' },
        { name: 'twitter', link: 'https://twitter.com' },
        { name: 'instagram', link: 'https://www.instagram.com/?hl=en' },
      ],
      actionLinks: [
        { name: 'Shop', link: '#' },
        { name: 'Plan my kitchen', link: '#' },
        { name: 'About us', link: '#' },
        { name: 'gallery', link: '#' },
      ],
      pretitle: 'Design and order your new kitchen online today',
      title: 'Bespoke & made to measure handmade kitchen design',
      cta: {
        link: '#',
        text: 'Order now',
      },
      about: {
        overline: 'Quality Craftmanship from build to delivery',
        title: 'Discover the beauty of a handmade kitchen',
        content:
          'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi eget est sit amet sapien venenatis maximus vel in urna. Nam mauris arcu, feugiat in finibus vitae, sollicitudin id purus. Ut imperdiet, magna eu pharetra tincidunt, mauris purus ultrices.',
        btnLink: '#',
        btnText: 'About us',
      },
    }
  },
}
</script>
<style lang="scss" scoped></style>
