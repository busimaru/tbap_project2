<template>
  <v-container>
    <h1>プロジェクト詳細</h1>
    <br>
    <v-card>
    <v-row
      v-for="j in justify"
      :key="j"
      :justify="j"
    >
      <v-col
        v-for="k in 2"
        :key="k"
        md="4"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
          One of two columns
        </v-card>
      </v-col>
    </v-row>
    </v-card>
    <v-card>
    </v-card>
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