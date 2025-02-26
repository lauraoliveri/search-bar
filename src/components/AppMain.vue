<script>
export default {
  data() {
    return { 
      search: "",
      postList: [
        {
          id: 1,
          title: "kitty",
          image: "https://unsplash.com/s/photos/cat"
        },
        { id: 2, title: "puppy", image: "https://unsplash.com/@joeyc"},
        {
          id: 3,
          title: "polar bear",
          image: "https://unsplash.com/@hansjurgen007"
        },
        {
          id: 4,
          title: "little lion",
          image: "https://unsplash.com/@hansjurgen007"
        },
        {
          id: 5,
          title: "little bird",
          image:"https://unsplash.com/@eugenechystiakov"
        },
        {
          id: 6,
          title: "fox",
          image:"https://unsplash.com/@introspectivedsgn"
        }
      ],
      filteredPosts: []
    }
  },
  methods: {

    // to perform search with button and to filter 
    performSearch() {
      if (!this.search) {
        this.filteredPosts = this.postList;
      }
      else {
        this.filteredPosts = this.postList.filter(post => 
        post.title.toLowerCase().includes(this.search.toLowerCase())
        );
      }
    }
  },
  mounted() {

    // to show all posts in the page when theres no search
    this.filteredPosts = this.postList; 
  }
}

</script>

<template>
  <div class="container-fluid">
    <nav class="navbar bg-body-tertiary">
      <!-- input search -->
      <form class="d-flex" role="search"  @submit.prevent="performSearch">
        <input v-model="search" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button @click="performSearch" class="btn btn-outline-primary" type="submit">Search</button>
      </form> 
    </nav>

    <!-- Posts -->
    <div v-if="filteredPosts.length" class="d-flex flex-wrap">
      <div v-for="post in filteredPosts" :key="post.id" class="card m-2" style="width: 12rem;">
        <img :src="post.image" class="card-img-top" :alt="post.title">
        <div class="card-body">
          <h5 class="card-title">{{post.title}}</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;


</style>
