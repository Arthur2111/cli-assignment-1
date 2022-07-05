<template>
  <div>
    <header>User Details</header>
    <user-data @set-user="setUser"></user-data>
  </div>
  <ul>
    <active-user
      v-for="detail in details"
      :key="detail.id"
      :id="detail.id"
      :username="detail.username"
      :age="detail.age"
    >
    </active-user>
  </ul>
  <div>
    <create-data @create-new-user="createNewUser"></create-data>
  </div>
</template>

<script>
export default {
  data() {
    return {
      details: [
        {
          id: "1",
          username: "Hwang",
          age: 25,
        },
        {
          id: "2",
          username: "Joey",
          age: 26,
        },
      ],
    };
  },
  methods: {
    setUser(user, num, id) {
      // .find returns the wanted detail in details (since detail.id === id)
      const updateNewUser = this.details.find(detail => detail.id === id );
      updateNewUser.username= user
      updateNewUser.age= +num
    },
    createNewUser(user,num,id) {
      const newUser= {
        id: id,
        username: user,
        age: num,
      }
      this.details.push(newUser)

    }
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: "Jost", sans-serif;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app li,
#app form {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app h1,
#app h2,
#app h3 {
  font-size: 2rem;
  color: #58004d;
  margin: 0 0 1rem 0;
  text-align: center;
  border: 10px;
}
#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
#app button:hover,
#app button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
#app input {
  font: inherit;
  padding: 0.15rem;
}
#app label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
#app form div {
  margin: 1rem 0;
}
</style>