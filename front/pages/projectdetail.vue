<template>
  <v-container >
    <v-toolbar dark class="mb-10">
      <v-toolbar-title>
        <span class ="font-weight-light">TEAM_TBAP</span>
        <span class = "me-2">プロジェクトタイトル</span>
      </v-toolbar-title>
      <v-btn text outlined >
        tab1
      </v-btn>
      <v-spacer/>
      <v-btn>
        <v-app-bar-nav-icon />
      </v-btn>
    </v-toolbar>
    <h1> 試しに記載</h1>
    <h2 class="display-1">試しに記載</h2> 
    <p class ="blue white--text">とりあえずそれっぽく記載</p>
    <p class ="blue lighten-4 green--text text--darken-4">色合い変えてみた</p>
    <h1> ボタン追加してみた </h1>
    <v-btn color ="pink">button</v-btn>
    <v-btn color ="pink white--text">
      <v-icon left>mdi-mail</v-icon>
      <span>send-e-mail</span>
    </v-btn>
    <v-btn color ="pink white--text">
      <v-icon>mdi-mail</v-icon>
      <span>send-e-mail</span>
    </v-btn>
    <v-btn rounded small outlined color ="pink">
      <v-icon small >mdi-heart-outline</v-icon>
    </v-btn>
    <v-btn depressed color ="pink">button</v-btn>
    <v-btn text outlined color ="pink">button</v-btn>
    <v-btn outlined class ="hidden-md-and-down">button</v-btn>
    <v-row wrap>
      <v-col xs="12" md="6">
        <v-btn block outlined class="primary">1</v-btn>
      </v-col>
      <v-col xs="12" md="6">
        <v-btn block outlined class="primary">2</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  name: 'ProjectDetail',
  data: () => ({
    justify: [
      'start',
      'center',
      'end',
      'space-around',
      'space-between',
      ],
    }),
}
</script>