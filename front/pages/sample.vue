<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-card v-if="students">
      <v-card-title>
        生徒情報一覧
        <v-spacer />
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="検索"
          sigle-line
        />
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="students"
        :items-per-page="5"
        :search="search"
        class="elevation-2"
      >
        <template v-slot:activator="{ on }">
          <v-btn fab small class="mb-2"
            @click="add"
          >
            <v-icon>
              mdi-plus
            </v-icon>
          </v-btn>
        </template>
        <template v-slot:item.actions="{ item }">
          <v-icon
            small
            @click="edit(item)"
          >
            mdi-pencil
          </v-icon>
          <v-icon
            small
            @click="remove(item)"
          >
            mdi-delete
          </v-icon>
        </template>
      </v-data-table>
    </v-card>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      headers: [
        { text: 'ID', value: 'id' },
        { text: '名前', value: 'name' },
        { text: '国語', value: 'japanese' },
        { text: '数学', value: 'math' },
        { text: '英語', value: 'english'},
        { text: '操作', value: 'actions'}
      ],
      student: {},
    }
  },
  computed: {
    students () {
      return this.$store.getters['getStudents']
    }
  },
  methods: {
    edit (student) {
      this.student = Object.assign({}, student)
      this.dialog = true
    },
    update () {
      const payload = { student: this.student }
      this.$store.commit('updateStudent', payload)
      this.close()
    },
    remove (student) {
      const payload = { student: student }
      this.$store.commit('removeStudent', payload)
    },
    close () {
      this.dialog = false
      this.student = {}
    },
    add (student) {
      this.student = {}
      this.dialog = true
    },
    create () {
      const payload = { student: this.student }
      this.$store.commit('addUser', payload)
      this.close()
    },
    isPersistedStudent () {
      return !!this.student.id
    },
    formTitle () {
      return this.isPersistedStudent ? '生徒情報編集' : '生徒情報追加'
    }
  }
}
</script>