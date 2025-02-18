<template>
  <div>
    <h1 class="text-center">Les meilleurs films</h1>
    <v-row no-gutters>

      <v-col v-for="item in data.results" :key="item" cols="10" class="g-5" sm="4" md="2">
        <v-card class="mx-auto $primary g-10" hover height="500" width="300">
          <v-card-item>
            <v-card-title class="text-center">
              {{ item.title }}
            </v-card-title>

            <v-img class="align-end text-white" height="200"
              :src="'https://image.tmdb.org/t/p/w500' + item.poster_path" />

            <v-card-subtitle class="mt-1">
              {{ item.release_date }}
            </v-card-subtitle>
          </v-card-item>

          <v-card-text>
            {{ item.overview }}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script setup lang="ts">
const { data } = await useFetch('https://api.themoviedb.org/3/movie/popular?api_key=7dc3e007b3f68e10b0cc01ea338f5593')

</script>

<style lang="scss">
$primary: red;
$text-center: "text-center";

body {
  color: $primary;
}
</style>