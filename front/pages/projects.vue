<template>
  <v-card v-if="items">
    <h1>プロジェクト一覧</h1>
  </v-card>
</template>
<script>
export default {
  name: 'ProjectIndex',
  data: () => ({
    items: [
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me 2' },
    ],
  }),
}
</script>