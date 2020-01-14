<template>
  <v-col cols=12 md=6>
    <v-card height="auto" class="pb-5">
      <h1>{{work.name}}</h1>
      <v-divider/>
      <v-img :src="require('../assets/images/'+ this.work.image)" height="240px" contain class="my-3"/>
      <v-divider/>
      <div class="mt-2">
        {{work.text}}
      </div>
      <div>
        {{work.text2}}
      </div>
      <div>
        {{work.text3}}
      </div>
      <v-divider/>
      <h3>使用技術</h3>
      <div v-for="skill in work.skills" :key="skill.name">
        {{skill.name}}
      </div>
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
