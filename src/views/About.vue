<template>
  <v-container text-center>
    <v-layout row wrap justify-center>
      <v-flex xs12>
        <h1>About</h1>
      </v-flex>

      <v-flex xs12 mt-2>
        <v-card>
          <v-card-title>
            <h1>Profile</h1>
          </v-card-title>
          <v-card-text class="text-sm-left">
              <h2 class="mb-2">Name：みの</h2>
              <div style="white-space:pre-wrap;">
                {{profile}}
              </div>
          </v-card-text>
        </v-card>
      </v-flex>

      <v-flex xs12 mt-2>
        <v-card>
          <v-card-title>
            <h1>Skill</h1>
          </v-card-title>
          <v-card-text>
            <v-list three-line>
              <template v-for="(item, index) in items">
                <v-list-tile :key="item.title" >
                  <v-list-tile-content>
                    <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    <br>
                    <v-list-tile-sub-title>
                      {{ item.body }}
                      <br/>
                      実務歴：{{ item.history }}
                    </v-list-tile-sub-title>
                  </v-list-tile-content>
                </v-list-tile>
                <v-divider class="my-3"
                  v-if="index + 1 < items.length"
                  :key="index"
                ></v-divider>
              </template>
            </v-list>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import skills from '../assets/skills.json'

export default {
  data(){
    return {
    items: skills,
    profile: 
    ` システムエンジニアをしています。
    業務では主にC#を使用して業務アプリケーションを開発・保守をしています。
    現在は、Web系の技術に興味を持ち勉強中です`
    }
  }
}
</script>