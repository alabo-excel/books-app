<template>
<div>
  <b-navbar type="light" variant="light">
      <b-navbar-brand tag="h1" class="mb-0">BooksA</b-navbar-brand>

    <b-nav-form class="ml-auto">
      <b-form-input class="mr-sm-2" placeholder="Search"></b-form-input>
      <b-button variant="outline-success" class="my-2 my-sm-0" type="submit">Search</b-button>
    </b-nav-form>
  </b-navbar>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
