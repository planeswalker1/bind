<template>
  <div class="container">
    <header>
      <h1>What is Vue Data Binding</h1>
      <p>
        It keeps your data (i.e. your Javascript variables, arrays etc) in sync with your DOM without you having to do anything.
        If we want to bind data to an attribute we can use v-bind: and use {{ property }} for everything else.
        If we want to dynamically change data we can use v-model:.
        This website showcases some practical uses of Vue data binding.
      </p>
    </header>
    <addBlog></addBlog>
  </div>
</template>

<script>
import newBlog from './components/new-blog.vue'

export default {
  components: {
    addBlog: newBlog
  },
  data() {
    return {
      property: '{{ property }}'
    };
  }
}
</script>

<style>
  html {
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }

  body {
    font-family: sans-serif;
    line-height: 1.5;
    margin: 0;
  }

  .container {
    margin: 0 auto;
    max-width: 1360px;
  }
</style>
