<template>
  <v-container
    id="landing-page"
    fluid
  >
    <v-row
      class="text-center"
      :class="{ 'pb-5': $vuetify.breakpoint.smAndDown }"
    >
      <v-col
        cols="12"
      >
        <h1 class="display-2 font-weight-bold">
          A G &amp; Sons
        </h1>
        <h1 class="display-2 font-weight-bold">
          Janitorial Cleaning Services
        </h1>
      </v-col>
      <v-col
        cols="12"
        sm="6"
        :class="{ 'pr-2': $vuetify.breakpoint.mdAndUp }"
      >
        <v-card
          outlined
          hover
        >
          <v-card-title class="textPrimary--text">
            Services
          </v-card-title>
          <v-expansion-panels
            accordion
          >
            <v-expansion-panel
              v-for="(item,i) in services"
              :key="i"
            >
              <v-expansion-panel-header>
                {{ item.title }}
                <template v-slot:actions>
                  <v-icon color="accent">
                    $expand
                  </v-icon>
                </template>
              </v-expansion-panel-header>
              <v-expansion-panel-content>
                {{ item.data }}
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-card>
      </v-col>
      <v-col
        cols="12"
        sm="6"
        :class="{ 'pl-2': $vuetify.breakpoint.mdAndUp }"
      >
        <v-card
          outlined
          hover
        >
          <v-card-title class="textPrimary--text">
            Contact Information
          </v-card-title>
          <v-card-text class="textSecondary--text text-left">
            we'll get back to you
          </v-card-text>
          <v-list
            class="text-left"
          >
            <v-list-item
              v-for="item in contactInfo"
              :key="item.title"
            >
              <v-list-item-avatar>
                <v-icon
                  :class="[item.iconClass]"
                  v-text="item.icon"
                />
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title v-text="item.information" />
              </v-list-item-content>

              <v-list-item-action>
                <v-btn
                  v-if="item.actionIcon"
                  icon
                >
                  <v-icon
                    color="default"
                    v-text="item.actionIcon"
                  />
                </v-btn>
              </v-list-item-action>
            </v-list-item>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
    <v-footer
      color="accent"
      absolute
      padless
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-col
          class="py-2 overline white--text text-center"
          cols="12"
        >
          Photo by
          <a
            href="https://www.pexels.com/@seven11nash?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels"
            class="white--text"
          >
            Marc Mueller
          </a>
          from
          <a
            href="https://www.pexels.com/photo/architectural-design-architecture-ceiling-chairs-380768/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels"
            class="white--text"
          >
            Pexels
          </a>
          . Aaron Thawe - {{ new Date().getFullYear() }}
        </v-col>
      </v-row>
    </v-footer>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      contactInfo: [
        { title: 'Address', information: '415 William Street, London, ON, Canada', icon: 'mdi-home', iconClass: 'default white--text', actionIcon: 'mdi-map-marker' },
        { title: 'Phone Number', information: '(519) 439-6151', icon: 'mdi-phone', iconClass: 'default white--text' },
        { title: 'Email', information: 'auckland@bell.net', icon: 'mdi-at', iconClass: 'default white--text', actionIcon: 'mdi-chevron-right-circle' },
      ],
      services: [
        { title: 'Weekly Cleaning', data: 'Our excellent staff will ensure that your offices are kept to a high standard of cleanliness, showing great care to abide by your company policies.' },
        { title: 'Building Maintenance', data: 'We can perform regular services to maintain the quality of your office environment, whether it requires refinishing floors, carpet cleaning, or window cleaning.' },
      ],
    }),
  }
</script>

<style scoped>
  #landing-page {
    background-image: linear-gradient(rgba(103,58,183,0.5), rgba(103,58,183,0.5)), url('../assets/clean-office.jpg');
    height: 100%;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: relative;
  }
  .white--text > a {
    text-decoration: none;
    font-style: italic;
  }
</style>
