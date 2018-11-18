<template>
  <div class="home">
    <h1>Add new person</h1>
    <div>
      Name: <input type="text" v-model="newPersonName">
      Bio: <input type="text" v-model="newPersonBio">
      <button v-on:click="createPerson()">Create person!</button>
    </div>
    <h1>Interesting People ({{ people.length }} total)</h1>
    <div v-for="person in people">
      <h2>{{ person.name }}</h2>
      <p>{{ person.bio }}</p>
      <button v-on:click="destroyPerson(person)">Destroy</button>
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      newPersonName: "",
      newPersonBio: "",
      people: [
        {
          name: "Bob",
          bio:
            "Small batch salvia Marfa chillwave delectus, odio forage art party laborum street art minim fixie locavore hoodie mollit.",
          bioVisible: true
        },
        {
          name: "Alice",
          bio:
            "Tattooed letterpress gluten-free ugh, adipisicing scenester church-key gentrify tousled gastropub pour-over Shoreditch asymmetrical lomo High Life.",
          bioVisible: true
        },
        {
          name: "Tibor",
          bio:
            "Incididunt photo booth ethical reprehenderit adipisicing. Echo Park readymade Bushwick distillery Tonx. +1 semiotics qui duis literally.",
          bioVisible: true
        },
        {
          name: "Živa",
          bio:
            "Excepteur shabby chic semiotics Marfa, quinoa try-hard polaroid pariatur banh mi selfies incididunt brunch trust fund. Ethical dolor PBR&B Tumblr.",
          bioVisible: true
        }
      ]
    };
  },
  created: function() {},
  methods: {
    createPerson: function() {
      var newPerson = {
        name: this.newPersonName,
        bio: this.newPersonBio,
        bioVisible: true
      };
      this.people.push(newPerson);
    },
    destroyPerson: function(inputPerson) {
      var index = this.people.indexOf(inputPerson);
      this.people.splice(index, 1);
    }
  },
  computed: {}
};
</script>
