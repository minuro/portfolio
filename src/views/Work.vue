<template>
  <v-container text-center>
    <v-layout row wrap justify-center>
      <v-flex xs12>
        <h1>Work</h1>
      </v-flex>
      <v-flex xs10 mt-2>
        <v-card>
          <v-card v-if="works.length == 0" class="pa-3">
            <h3>--- 開発中 ---</h3>
          </v-card>
          <v-row>
            <WorkComponent v-for="work in works" :key="work.name" :work="work"/>
          </v-row>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import works from '../assets/works.json'
import WorkComponent from '../components/WorkComponent'

export default {
  components: {
    WorkComponent
  },
  data() {
    return {
      works: works
    }
  }
}
</script>