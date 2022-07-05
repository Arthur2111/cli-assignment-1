<template>
<form>
  <section>
  <div>
    <h2>Username: <span> {{ username }} </span></h2>
  </div>
  <div>
    <h3>Age: {{ age }}</h3>
  </div>
  <div>
    <h3>ID: {{ id }}</h3>
  </div>
  </section>
  </form>
  

</template>

<script>
export default {
  props: {
    username: String,
    age: {
      type: Number
    },
    id: String,
  },
};
</script>

<style scoped>

span {
  color: blue;
}

section {
  margin: 2rem auto;
  border-radius: 2rem;
}

</style>
