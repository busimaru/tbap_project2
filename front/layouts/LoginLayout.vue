<!-- ログイン画面のレイアウト作成中 -->
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
    <v-main>
      <v-container fill-height>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default{
    data () {
    return {
      clipped: true,
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
          icon: 'mdi-home-search',
          title: 'post',
          to: '/post'
        },
        {
          icon: 'mdi-vuetify',
          title: 'test',
          to: '/test'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>