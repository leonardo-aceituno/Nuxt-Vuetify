<template>
  <v-card class="mx-auto" max-width="344">
    <v-img :src="character.image" contain></v-img>

    <v-card-title> {{ character.name }} </v-card-title>

    <!-- <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle> -->

    <v-card-actions>
      <v-btn color="orange lighten-2" text> Explore </v-btn>

      <v-spacer></v-spacer>

      <v-btn icon @click="show = !show">
        <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card class="mx-auto" tile>
          <v-list-item two-line>
            <v-list-item-content>
              <v-list-item-title>Species</v-list-item-title>
              <v-list-item-subtitle>{{
                character.species
              }}</v-list-item-subtitle>

              <v-list-item-title class="mt-2">Gender</v-list-item-title>
              <v-list-item-subtitle>{{
                character.gender
              }}</v-list-item-subtitle>

              <v-list-item-title class="mt-2">Origin</v-list-item-title>
              <v-list-item-subtitle>{{
                character.origin.name
              }}</v-list-item-subtitle>

              <v-list-item-title class="mt-2">Location</v-list-item-title>
              <v-list-item-subtitle>{{
                character.location.name
              }}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script>
export default {
  props: {
    character: { type: Object },
  },
  data() {
    return { show: false };
  },
};
</script>
