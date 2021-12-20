<template>
  <v-container>
    <v-row>
      <v-col
        v-for="(character, index) in characters"
        :key="index"
        cols="12"
        sm="4"
      >
        <Card :character="character" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Card from "@/components/Card";
import axios from "axios";

export default {
  components: { Card },

  data() {
    return {
      // personajes: [
      //   {
      //     id: 1,
      //     nombre: "Morty",
      //     imagen: "https://rickandmortyapi.com/api/character/avatar/2.jpeg",
      //   },
      //   {
      //     id: 2,
      //     nombre: "Rick",
      //     imagen: "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
      //   },
      //   {
      //     id: 3,
      //     nombre: "Summer",
      //     imagen: "https://rickandmortyapi.com/api/character/avatar/3.jpeg",
      //   },
      //   {
      //     id: 4,
      //     nombre: "Beth",
      //     imagen: "https://rickandmortyapi.com/api/character/avatar/4.jpeg",
      //   },
      //   {
      //     id: 5,
      //     nombre: "Jerry",
      //     imagen: "https://rickandmortyapi.com/api/character/avatar/5.jpeg",
      //   },
      // ],
      characters: null,
    };
  },
  mounted() {
    const url =
      "https://rickandmortyapi.com/api/character/[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21]";
    axios.get(url).then((response) => (this.characters = response.data));
  },
};
</script>
