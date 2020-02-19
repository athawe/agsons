<template>
  <v-app>
    <v-app-bar
      color="default"
      dense
      dark
      app
    >
      <v-toolbar-title class="headline text-uppercase">
        <span>A G &amp; Sons</span>
      </v-toolbar-title>
      <v-spacer />
      <v-btn icon>
        <v-icon
          @click="changeTheme"
          v-text="colourMode"
        />
      </v-btn>
    </v-app-bar>
    <v-content>
      <front-page />
    </v-content>
  </v-app>
</template>

<script>
  import FrontPage from './components/FrontPage'

  export default {
    name: 'App',
    components: {
      FrontPage,
    },
    data: () => ({
    }),
    computed: {
      colourMode () {
        if (!this.$vuetify.theme.dark) {
          return 'mdi-moon-waning-crescent'
        } else {
          return 'mdi-white-balance-sunny'
        }
      },
    },
    methods: {
      changeTheme () {
        if (!this.$vuetify.theme.dark) {
          this.$vuetify.theme.dark = true
        } else {
          this.$vuetify.theme.dark = false
        }
      },
    },
  }
</script>
