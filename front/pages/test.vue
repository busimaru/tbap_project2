<template>
  <v-card v-if="items">
    <h1>TEST </h1>
  </v-card>
</template>
<script>
export default {
  name: 'TestPage',
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