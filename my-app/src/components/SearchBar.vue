<template>
  <div class="hello">
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput: (event) => {
      console.log(event.target.value);
    }
  }
  /* props: {
    msg: String
  } */
}
</script>

<!-- <style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #b94295;
}
</style> -->
