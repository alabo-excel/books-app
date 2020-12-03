<template>
  <div class="m-1">
    <h1>Books</h1>
    <b-card-group columns>
      <b-card
        img-src=""
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem"
        class="mb-2 col-3"
        v-for="(movie, index) in movies"
        :key="index"
      >
        <b-card-text>
          <h5>{{ index }} {{ movie.volumeInfo.title }}</h5>
          <div>
          </div>
          <div class="text-left mt-3">
            <p>Published By: {{ movie.volumeInfo.publisher }}</p>
            <p>Published On:{{ movie.volumeInfo.publishedDate }}</p>
          </div>
        </b-card-text>
        <b-button href="#" variant="outline-success" @click="openDetails(index)"
          >Read More</b-button
        >
      </b-card>
    </b-card-group>

    <div v-if="this.num != null">
      <b-modal v-b-modal.modal-lg  v-model="modal">
        <h1>
          {{ this.movies[this.num].volumeInfo.title }}
        </h1>
        <p>{{ this.movies[this.num].volumeInfo.description }}</p>
      </b-modal>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      movies: [],
      desc: [],
      modal: false,
      num: null
    };
  },
  created() {
    const options = {
      method: "GET",
      url: "https://google-books.p.rapidapi.com/volumes",
      params: { key: "AIzaSyAOsteuaW5ifVvA_RkLXh0mYs6GLAD6ykc" },
      headers: {
        "x-rapidapi-key": "d82821146dmsh0ea8a649aa47896p17a7fbjsn4c87553327e7",
        "x-rapidapi-host": "google-books.p.rapidapi.com",
      },
    };

    axios
      .request(options)
      .then((response) => {
        this.movies = response.data.items;
        
      })
      .catch((error) => {
        console.error(error);
      });
  },
  methods: {
    openDetails(index) {
      this.modal = true;
      this.num = index
    },
  },
};
</script>

<style></style>
