<template>
  <v-container>
    <div v-for="meme in memes" :key="meme.id" class="py-5">
      <router-link :to="`/meme/${meme.id}`">
        <meme
          class="mx-auto mt-6"
          :top="meme.topText"
          :bottom="meme.bottomText"
          :imageURL="meme.imageURL"
        />
      </router-link>
    </div>
  </v-container>
</template>

<script>
import { db } from "../firebase";
import Meme from "./Meme";

export default {
  components: { Meme },
  data() {
    return {
      memes: [],
    };
  },

  mounted() {
    db.collection("memes").onSnapshot((snap) => {
      const memes = snap.docs.map((doc) => {
        return {
          ...doc.data(),
          id: doc.id,
        };
      });
      this.memes = memes;
    });
  },
};
</script>

<style></style>
