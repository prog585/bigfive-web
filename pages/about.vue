<template>
  <div class="about">
    <h1>Team</h1>

    <v-container class="my-5">
      <v-layout row wrap>
        <v-flex xs12 sm12 md6 v-for="person in team" :key="person.name">
          <v-card flat width="400px" class="text-xs-center ma-3">
            <v-img :src="person.avatar" height="400px" color="#eeeeee"></v-img>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
              <a :href="person.github" target="_blank">
                <v-icon>{{ mdiGithub }}</v-icon>
              </a>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import { mdiGithub } from '@mdi/js'
export default {
  name: 'About',
  head () {
    return {
      title: this.$t('about.seo.title'),
      meta: [
        { hid: 'title', name: 'title', content: this.$t('about.seo.title') },
        { hid: 'description', name: 'description', content: this.$t('about.seo.description') },
        { hid: 'keywords', name: 'keywords', content: this.$t('seo.keywords') },
        // Open Graph
        { hid: 'og:title', name: 'og:title', content: this.$t('about.seo.title') },
        { hid: 'og:description', name: 'og:description', content: this.$t('about.seo.description') },
        { hid: 'twitter:title', name: 'twitter:title', content: this.$t('about.seo.title') },
        { hid: 'twitter:description', name: 'twitter:description', content: this.$t('about.seo.description')  }
      ]
    }
  },
  data () {
    return {
      mdiGithub,
      team: [
        {
          name: 'JONAS MACCYBER ENGE',
          role: 'FOUNDER',
          avatar: require('@/assets/jonas.jpg'),
          github: 'https://github.com/maccyber'
        },
        {
          name: 'GEIR GÅSODDEN',
          role: 'CO FOUNDER',
          avatar: require('@/assets/geir.jpg'),
          github: 'https://github.com/zrrrzzt'
        },
        {
          name: 'OLE MORTEN AMUNDSEN',
          role: 'WEB DEVELOPER',
          avatar: require('@/assets/ole_morten.jpg'),
          github: 'https://github.com/oma'
        },
        {
          name: 'PÅL ANDRÈ SUNDT',
          role: 'ART DIRECTOR',
          avatar: require('@/assets/paal.jpg'),
          github: 'https://github.com/str1fe'
        },
        {
          name: 'MATHIAS MOXNES',
          role: 'WEB DEVELOPER',
          avatar: require('@/assets/mathias.jpg'),
          github: 'https://github.com/moxnes'
        }
      ]
    }
  }
}
</script>
