<script>
import SecondPart from './SecondPart.vue';

export default {
  name: 'app',
  components: { SecondPart },
  data () {
    return {
      people: [
        {
          firstName: 'Hello',
          lastName: 'Kitty',
          id: 'hellok'
        },
        {
          firstName: 'Peppa',
          lastName: 'Pig',
          id: 'peppap'
        },
        {
          firstName: 'SpongeBob',
          lastName: 'SquarePants',
          id: 'spong'
        },
      ],
      peopleInfo: [
        {
          address: {
            street: 'Pink St.',
            country: 'Japan'
          },
          'Secret Info': {
            dont: 'showme'
          },
          personId: 'hellok',
          quote: 'Meow',
          status: 'Fictional'
        },
        {
          address: {
            street: 'Pineapple under the sea',
            country: 'The sea'
          },
          'Want to know more?': {
            dont: 'showme'
          },
          personId: 'spong',
          quote: 'Where is Patrick?',
          status: 'Fictional'
        },
        {
          address: {
            street: 'Pig St.',
            country: 'Mud Puddles Country'
          },
          'Secret Info': {
            dont: 'showme'
          },
          'Want to know more?': {
            dont: 'showme'
          },
          personId: 'peppap',
          quote: 'My most favorite thing in the whole world is jumping up and down in muddy puddles!',
          status: 'Fictional'
        },
      ],
      selectedCharacter: {},
      selectedCharacterInfo: {}
    }
  },
  methods: {
    displayPerson(person) {
      this.selectedCharacter = person,
      this.selectedCharacterInfo = this.peopleInfo.filter( info => {return info.personId == person.id})[0]
    }
  }
}
</script>

<template>
  <div id="app">
    <h1>Toucan Object explorer</h1>
    <h2>Test by Mariem Belgacem</h2>

    <!-- First part : Display a list and some information -->
    <div class="selected-character" >
      <p>{{ selectedCharacter.firstName }} {{ selectedCharacter.lastName }}</p>
      <div v-for="(key,val) in selectedCharacterInfo">
        <p>{{ val }} : {{ typeof key === 'object' ? '[+]': key }} </p>
      </div>
    </div>
    <ul>
      <li v-for="person in people" @click="displayPerson(person)" v-bind:class="{ active: person.id == selectedCharacter.id }" >
        {{ person.firstName }} {{ person.lastName }}
      </li>
    </ul>
    
    <SecondPart />
  </div>
</template>

<style lang="css">

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

li {
  display: inline-block;
  margin: 10px;
  padding: 1.5rem;
  background-color: #e1e1e1;
  color: #2c3e50;
  font-size: 16px;
  border-radius: 8px;
  min-width: 450px;
}

li.active {
  background-color: #a3a3a3;
}

a {
  color: #42b983;
}
.selected-character {
  text-align: left;
  padding: 1rem;
  font-size: 16px;
  color: #2c3e50;
}
</style>
