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
    width: 50%;
  }

  /* link styles */
  ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
    width: 100%;
  }

  li {
    margin-right: 10px;
  }

  a {
    background-color: transparent;
    color: #007bff;
    text-decoration: none;
  }

  a:hover {
    color: #0056b3;
    text-decoration: underline;
  }

  h1,
  form {
    margin: 0 auto;
    max-width: 600px;
  }

  .heading {
    margin: 0;
    max-width: unset;
  }

  h1 {
    margin-top: 1em;
  }

  p {
    margin-bottom: 0;
  }

  .form__header,
  .form__fields,
  .form__controls {
    padding: 5px;
  }

  /* form control styles */
  .group {
    margin-bottom: 10px;
  }

  .group__label {
    display: block;
    margin: .5em 0;
  }

  .group__input {
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: .25em;
    color: #495057;
    display: block;
    font-size: 1em;
    line-height: 1.5;
    padding: .375em .75em;
    transition: border-color .15s ease-in-out,box-shadow .15s ease-in-out;
  }

  .group__input:focus {
    background-color: #fff;
    border-color: #80bdff;
    box-shadow: 0 0 0 0.2em rgba(0,123,255,.25);
    color: #495057;
    outline: 0;
  }

  .group__textarea {
    background-clip: padding-box;
    background-color: #fff;
    border: 1px solid #ced4da;
    border-radius: .25em;
    color: #495057;
    display: block;
    line-height: 1.5;
    overflow: auto;
    padding: .375em .75em;
    resize: vertical;
    transition: border-color .15s ease-in-out,box-shadow .15s ease-in-out;
  }

  .group__textarea:focus {
    background-color: #fff;
    border-color: #80bdff;
    box-shadow: 0 0 0 0.2em rgba(0,123,255,.25);
    color: #495057;
    outline: 0;
  }

  .group__input,
  .group__textarea {
    width: 100%;
  }

  .preview {
    border: 1px dotted #ccc;
    margin: 30px 0;
    padding: 10px 20px;
  }

  /* radio button styles */
  .checkbox,
  .selectbox {
    margin: 10px 0;
  }

  /* The container */
  .radio {
      cursor: pointer;
      display: inline-block;
      margin: 10px;
      padding-left: 25px;
      position: relative;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
  }

  /* Hide the browser's default checkbox */
  .radio .radio__checkbox {
      display: none;
      /* cursor: pointer;
      opacity: 0;
      position: absolute; */
  }

  /* Create a custom checkbox */
  .radio__checkmark {
      background-color: #eee;
      height: 17px;
      position: absolute;
      top: 0;
      left: 0;
      width: 17px;
  }

  /* On mouse-over, add a grey background color */
  .radio:hover .radio__checkbox ~ .radio__checkmark {
      background-color: #ccc;
  }

  /* When the checkbox is checked, add a blue background */
  .radio .radio__checkbox:checked ~ .radio__checkmark {
      background-color: #007bff;
  }

  /* Create the checkmark/indicator (hidden when not checked) */
  .radio__checkmark:after {
      content: "";
      display: none;
      position: absolute;
  }

  /* Show the checkmark when checked */
  .radio__checkbox:checked ~ .radio__checkmark:after {
      display: block;
  }

  /* Style the checkmark/indicator */
  .radio__checkmark:after {
      border: solid white;
      border-width: 0 3px 3px 0;
      height: 10px;
      top: 3px;
      left: 6px;
      -webkit-transform: rotate(45deg);
      -ms-transform: rotate(45deg);
      transform: rotate(45deg);
      width: 5px;
  }

  /* select input styles */
  .select {
    -moz-appearance: none;
    -webkit-appearance: none;
    background: #fff url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 4 5'%3E%3Cpath fill='%23333' d='M2 0L0 2h4zm0 5L0 3h4z'/%3E%3C/svg%3E") no-repeat right .75rem center;
    background-size: 8px 10px;
    -webkit-background-size: 8px 10px;
    border: 1px solid rgba(0,0,0,.15);
    border-radius: .25em;
    color: #464a4c;
    cursor: pointer;
    display: inline-block;
    height: calc(2.25em + 2px);
    line-height: 1.25;
    max-width: 100%;
    padding: .375rem 1.75rem .375rem .75rem;
    vertical-align: middle;
  }

  .select:focus {
    border-color: #5cb3fd;
    cursor: pointer;
    outline: 0;
  }

  .select:active {
    border-color: #5cb3fd;
    cursor: pointer;
    outline: 0;
  }

  .preview__categories {
    margin-bottom: 0;
  }

  @media screen and (max-width: 800px) {
    .container {
      padding: 20px;
      width: 80%;
    }

    input,
    textarea {
      width: 100%;
    }
  }

  @media screen and (max-width: 500px) {
    .container {
      padding: 10px;
      width: 90%;
    }
  }
</style>
