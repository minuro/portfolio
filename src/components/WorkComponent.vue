<template>
  <v-col cols=12 md=6>
    <v-card height="450px">
      <h1>{{work.name}}</h1>
      <v-divider/>
      <v-img :src="require('../assets/images/'+ this.work.image)" height="240px" contain class="my-3"/>
      <v-divider/>
      <h2 class="mt-2">
        <a :href="work.url" target="_blank">
          <v-btn rounded color="success" min-width="120px">リンク</v-btn>
        </a>
      </h2>
      <h2 class="mt-2">
        <a :href="work.githubURL" target="_blank">
          <v-btn rounded color="success" min-width="120px">github</v-btn>
        </a>
      </h2>
    </v-card>
  </v-col>
</template>

<script>
export default {
  props: ['work']
}
</script>
