<template>
  <v-container text-center>
    <v-layout row wrap justify-center>
      <v-flex xs12>
        <h1>Link</h1>
      </v-flex>

      <v-flex xs12 mt-2>
        <v-card>
          <v-card-text>
            <v-list two-line>
              <template v-for="(link, index) in links">
                <v-list-tile :key="link.title">
                  <v-list-tile-content>
                    <v-list-tile-title @click="PageLink(link.address)">
                      <h2>
                        {{ link.title }}
                      </h2>
                    </v-list-tile-title>
                  </v-list-tile-content>
                </v-list-tile>
                <v-divider class="my-3"
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
export default {
  data() {
    return {
      links: [
        {
          title: 'twitter',
          address: 'https://twitter.com/it_minuro57'
        },
        {
          title: 'qiita',
          address: 'https://qiita.com/minuro'
        },
        {
          title: 'GitHub',
          address: 'https://github.com/minuro'
        }
      ]
    }
  },
  methods: {
      PageLink(address){
        window.open(address, '_blank'); 
      }
  }
}
</script>
