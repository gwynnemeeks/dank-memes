<template>
  <div>
    <form @submit.prevent="generateMeme">
      <input placeholder="Image URL" type="text" v-model="imageURL" />
      <input placeholder="Top Text" type="text" v-model="topText" />
      <input placeholder="Bottom Text" type="text" v-model="bottomText" />
      <button type="submit">Generate Meme!</button>
    </form>
    <div v-if="showMeme">
      <meme :top="topText" :bottom="bottomText" :imageURL="imageURL" />
    </div>
  </div>
</template>

<script>
import Meme from "./Meme.vue";

export default {
  components: { Meme },
  data() {
    return {
      imageURL: "",
      topText: "",
      bottomText: "",
      showMeme: false,
    };
  },
  methods: {
    generateMeme() {
      console.log("building a meme....");
      this.showMeme = true;
    },
  },
};
</script>

<style></style>
