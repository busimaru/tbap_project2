<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn depressed rounded>
        <span>Sign Out</span>
        <v-icon right large>
          mdi-exit-to-app
        </v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        },
        //ここから試しに追加
        {
          icon: 'mdi-account-box-multiple',
          title: 'Users',
          to: '/users'
        },
        {
          icon: 'mdi-domain',
          title: 'sample',
          to: '/sample'
        },
        {
          icon: 'mdi-exit-run',
          title: 'login',
          to: '/login'
        },
        {
          icon: 'mdi-newspaper-variant',
          title: 'projects',
          to: '/projects'
        },
        {
          icon: 'mdi-newspaper',
          title: 'project detail',
          to: '/projectdetail'
        },
        {
          icon: 'mdi-home-search',
          title: 'post',
          to: '/post'
        },
        {
          icon: 'mdi-vuetify',
          title: 'test',
          to: '/test'
        },
        {
          icon: 'mdi-calendar',
          title: 'calender',
          to: '/calender'
        },
      ],
      miniVariant: true,
      right: false,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
}
</script>
