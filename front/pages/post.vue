<template>
  <v-card>
    <v-card-title>
      郵便番号取得
      <v-spacer />
      <v-text-field
        v-model="zipcode"
        append-icon="mdi-magnify"
        label="検索"
        sigle-line
      />
    </v-card-title>
    <v-btn 
      class="ma-4"
      @click=fetch 
      >
      検索開始
    </v-btn>
    <!-- リストで出せるように改造中 v-for= in-->
    <ul>
      <li v-for="value in result">
        {{ value }}
      </li>
    </ul>
  </v-card >
</template>
<script>
export default {
  name: 'Post',
  data:() => {
    return {
      zipcode:'',
      result: { "address1": "",
			          "address2": "",
			          "address3": "",
			          "kana1": "",
			          "kana2": "",
			          "kana3": "",
			          "prefcode": "",
			          "zipcode": ""
      },
      message: null,
    }
  },
  methods: {
    async fetch() {
      const params = { zipcode: this.zipcode }
      const res = await this.$axios.get("/api/search", { params })
      this.result = res.data.results[0]
      this.message = res.data.message
    },
  },
}
</script>