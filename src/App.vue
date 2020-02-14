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
        <v-icon>mdi-moon-waning-crescent</v-icon>
      </v-btn>
      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on }">
          <v-btn
            icon
            v-on="on"
          >
            <v-icon>mdi-menu</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in sections"
            :key="index"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
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
      sections: [
        { title: 'Home' },
        { title: 'Services' },
        { title: 'Contact Us' },
      ],
    }),
  }
</script>
