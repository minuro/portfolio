<template>
  <v-container text-center>
    <v-layout row wrap justify-center>
      <v-flex xs12>
        <h1>Link</h1>
      </v-flex>

      <v-flex xs10 mt-2>
        <v-card>
          <v-card-text>
            <v-list two-line>
              <template v-for="(link, index) in links">
                <v-list-item :key="link.title" :href="link.address" target="_blank">
                  <v-list-item-content>
                    <v-list-item-title>
                      <h2>
                        {{ link.title }}
                      </h2>
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-divider
                  v-if="index + 1 < links.length"
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
import links from '../assets/links.json'

export default {
  data() {
    return {
      links: links
    }
  }
}
</script>
