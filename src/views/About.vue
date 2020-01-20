<template>
  <v-container text-center>
    <v-layout row wrap justify-center>
      <v-flex xs12>
        <h1>About</h1>
      </v-flex>

      <v-flex xs10 md8 mt-2>
        <v-card>
          <v-card-title>
            <h1>Profile</h1>
          </v-card-title>
          <v-card-text class="text-left">
              <h2 class="mb-2">Name：minuro</h2>
              <div style="white-space:pre-wrap;">
                {{profile}}
              </div>
          </v-card-text>
        </v-card>
      </v-flex>

      <v-flex xs10 md8 mt-2>
        <v-card>
          <v-card-title>
            <h1>Skill</h1>
          </v-card-title>
          <v-card-text>
            <v-list three-line>
              <template v-for="(item, index) in items">
                <v-list-item :key="item.title" >
                  <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                    <br>
                    <v-list-item-subtitle>
                      {{ item.body }}
                      <br/>
                      実務歴：{{ item.history }}
                    </v-list-item-subtitle>
                  </v-list-item-content>
                </v-list-item>
                <v-divider
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
    業務では主にC#を使用して業務アプリケーションの開発・保守をしています。
    現在は、Web系の技術に興味を持ち勉強中です。`
    }
  }
}
</script>