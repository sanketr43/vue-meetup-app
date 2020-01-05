<template>
  <v-app>
    <div>
      <v-app-bar color="deep-purple accent-4" dark >
        <v-app-bar-nav-icon class="hidden-md-and-up" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

        <v-toolbar-title><router-link to="/" class="link">Vue MeetUp</router-link></v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon class="hidden-sm-and-down" v-for="item in menuItems" :key="item.title">
          <router-link :to="item.link" class="link"><v-icon>{{ item.icon }}</v-icon></router-link>
        </v-btn>

      </v-app-bar>
      <v-navigation-drawer
      v-model="drawer"
      absolute
      left
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item v-for="item in menuItems" :key="item.title" :to="item.link">
            <v-icon left>{{ item.icon }}</v-icon>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    </div>
    <main>
      <router-View></router-View>
    </main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    menuItems: [
      { icon: 'mdi-account-supervisor', title: 'View Meetup', link: '/meetups' },
      { icon: 'mdi-map-marker-outline', title: 'Organize Meetup', link: '/meetup/new' },
      { icon: 'mdi-account-circle-outline', title: 'Profile', link: '/profile' },
      { icon: 'mdi-account-plus', title: 'Sign Up', link: '/signup' },
      { icon: 'mdi-lock-open', title: 'Sign In', link: '/signin' }
    ]
  }),

  watch: {
    group () {
      this.drawer = false
    }
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.link
  text-decoration: none
  color: #ffffff !important
</style>
