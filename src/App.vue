<template>
  <v-app>
    <v-app-bar app color="pink lighten-2" light>
      <h1>Vue Meme Forum</h1>
      <v-spacer></v-spacer>
      <router-link to="/create">
        <v-btn text>Create</v-btn>
      </router-link>
      |
      <router-link to="/feed">
        <v-btn text> Memes </v-btn>
      </router-link>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {};
</script>

<style scoped>
a {
  text-decoration: none;
}
h1 {
  color: rgb(83, 35, 49);
}
.router-link-active .v-btn {
  color: rgb(83, 35, 49);
}
</style>
