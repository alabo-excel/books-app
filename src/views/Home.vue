<template>
  <div class="home">
    <navBar />
    <books />
  </div>
</template>

<script>
// @ is an alias to /src
import navBar from '@/components/navBar.vue'
import books from '@/components/books.vue'

export default {
  name: 'Home',
  components: {
    navBar,
    books
  }
}
</script>
