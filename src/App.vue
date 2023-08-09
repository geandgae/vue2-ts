<template>
  <v-app>
    <ul class="mt-16">
      <li><router-link to="/">home</router-link></li>
      <li @click="link('/')" style="cursor: pointer;">home</li>
      <li @click="link('/about')" style="cursor: pointer;">about</li>
    </ul>

    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'App',

  data: () => ({
    path: 'null: String'
  }),
  methods: {
    // link (val: string) {
    //   this.path = val
    //   console.log(this.path)
    //   this.$router.push({
    //     path: `${val}`
    //   }).catch(() => undefined)
    // }
    link (val: string) {
      this.path = val
      // console.log(this.path)
      this.$router.push({
        path: `${val}`
      }).catch(() => {})
    }
  }
})
</script>
