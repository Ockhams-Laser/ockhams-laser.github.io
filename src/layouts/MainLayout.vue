<template lang="pug">
q-layout(view='lHh Lpr lFf')
  q-header.flat(elevated)
    q-toolbar
      q-btn(flat @click='leftDrawerOpen = !leftDrawerOpen' aria-label='Menu' icon='menu')
      q-toolbar-title.q-ml-none
        i.fas.fa-sun.fa-2x.q-mr-sm
        | Ockham His Razor

        
      div(style="vertical-align: middle;") Engenho Novo v{{ $q.version }}
  q-drawer(v-model='leftDrawerOpen' show-if-above bordered content-class='bg-grey-1')
    q-list
      q-item-label.text-grey-8(header).
        
        Essential Links
        
      essentiallink(v-for='link in essentialLinks' :key='link.title' v-bind='link').
        
        
  q-page-container
    router-view.
      
      
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>

<style>

i, .material-icons {
  vertical-align: middle !important;
}
