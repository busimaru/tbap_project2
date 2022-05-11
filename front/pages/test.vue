<template>
  <div>
  <h1>テスト用のページ。色々試す用</h1>
  <h2>バナー作ってみた</h2>
  <v-banner two-line>
    <v-avatar
      slot="icon"
      color="deep-purple accent-4"
      size="40"
    >
      <v-icon
        icon="mdi-lock"
        color="white"
      >
        mdi-lock
      </v-icon>
    </v-avatar>

    Three line text string example with two actions. One to two lines is preferable. Three lines should be considered the maximum string length on desktop in order to keep messages short and actionable.

    <template v-slot:actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Action
      </v-btn>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Action
      </v-btn>
    </template>
  </v-banner>
  <v-banner two-line>
    <v-avatar
      slot="icon"
      size="40"
    >
      <v-icon
        icon="mdi-lock"
      >
        mdi-lock
      </v-icon>
    </v-avatar>
    test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.test.
    <template v-slot:actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Action
      </v-btn>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Action
      </v-btn>
    </template>
  </v-banner>
  <h2>アラート出してみた</h2>
  <v-container>
    <v-alert
      type = "info"
      border = "left"
      color-border
      color = "red"
    >お試し</v-alert>
    <v-alert
      dismissible
      v-model = "alert"
      border = "left"
      color-border
      type="success"
    >お試し2</v-alert>
    <div class="text-center mb-4">
      <v-btn
        v-if = "alert == false"
        color= "primary"
        @click="alert = !alert"
      >
        SET
      </v-btn>
    </div>
    <v-alert
      border="right"
      colored-border
      type="info"
      elevation="2"
    >お試し3</v-alert>
    <v-alert
      color = "green"
      text
      border="right"
      type="info"
      elevation="2"
    >お試し4</v-alert>
  </v-container>
  <h2>とりあえず作成</h2>
  <v-card class ="mx-4">
    <v-responsive :aspect-ratio="5/1">
      <v-card-title>
        <v-avatar
          color="primary"
          size="40"
        >
          <v-icon dark>
            mdi-alarm
          </v-icon>
        </v-avatar>
        カード関連
      </v-card-title>
        <v-row justify="space-around">
          <v-avatar color="indigo">
            <v-icon dark>
              mdi-account-circle
            </v-icon>
          </v-avatar>
          <v-badge
            bordered
            bottom
            color="deep-purple accent-4"
            dot
            offset-x="10"
            offset-y="10"
          >
            <v-avatar>
              <img
                src="https://cdn.vuetifyjs.com/images/john.jpg"
                alt="John"
              >
            </v-avatar>
          </v-badge>

          <v-avatar color="red">
            <span class="white--text text-h5">CJ</span>
          </v-avatar>
        </v-row>
    </v-responsive>
  </v-card>
  <v-card class ="mx-4">
    <v-card-title>
      ユーザー一覧作ってみた
    </v-card-title>
  </v-card>
  </div>
</template>
<script>
export default {
  name: 'Test',
  data:() =>{
    return{
      alert: false
    }
  }
}
</script>