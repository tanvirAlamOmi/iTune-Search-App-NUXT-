<template>
  <div
  id="e3"
  style="max-width: 800px; margin: auto;"
  class="grey lighten-3"
  >
    <v-container
      fluid
      style="min-height: 0;"
      grid-list-lg
    >
      <v-layout row wrap>

        <v-flex md12>
          <v-card target="_blank" :href="url" :color="color" class="white--text">
            <v-container fluid grid-list-lg>
              <v-layout row>
                <v-flex md7>
                  <div>
                    <div class="headline">{{title}}</div>
                    <div>{{artistName}}</div>
                  </div>
                </v-flex>
              <v-spacer/>
                <v-flex md5>
                <v-avatar
                class="ma-3"
                size="125"
                tile
              >
                <v-img :src="image"></v-img>
              </v-avatar>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card>
        </v-flex>

      </v-layout>
    </v-container>

  </div>

</template>
<script>
export default {
  props: ['title', 'image', 'artistName', 'url', 'color']
}
</script>