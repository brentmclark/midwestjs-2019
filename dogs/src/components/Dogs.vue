<template>
  <div class="dogs">
    <table v-if="dogs.length > 0">
      <thead>
        <tr>
          <th>Name</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="dog in dogs" :key="dog.name">
          <td>{{ dog.name }}</td>
        </tr>
      </tbody>
    </table>
    <div>
      <form @submit.prevent="handleSubmit">
        <label>Dog Name: </label>
        <input type="text" placeholder="Dog Name" />
        <button type="submit">Add Dog</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dogs',
  data() {
    return {
      dogs: []
    }
  },
  methods: {
    handleSubmit(e) {
      const {elements} = e.target
      this.dogs = this.dogs.concat([{name: elements[0].value}])
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
  color: #42b983;
}
</style>
