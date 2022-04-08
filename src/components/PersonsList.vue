<template>
  <div class="content">
    <div class="list">
      <div
        v-for="person in persons"
        :key="person.email"
        v-on:click="selectPerson(person)"
        class="person"
      >
        {{ person.name }}
      </div>
    </div>
    <PersonComponent v-if="selectedPerson" v-bind:person="selectedPerson" />
  </div>
</template>

<script>
import PersonComponent from "./Person.vue";

export default {
  name: "PersonsList",
  components: {
    PersonComponent,
  },
  data() {
    return {
      selectedPerson: null,
      selectPerson: (person) => {
        this.selectedPerson = { ...person };
      },
      persons: [
        {
          name: "Ion Creanga",
          phone: "+37360000001",
          email: "creanga@mail.com",
        },
        {
          name: "Mihai Eminescu",
          phone: "+37360000002",
          email: "eminescu@mail.com",
        },
        {
          name: "Lucian Blaga",
          phone: "+37360000003",
          email: "blaga@mail.com",
        },
      ],
    };
  },
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content {
  display: flex;
  align-items: center;
}

.list {
  display: flex;
  flex-direction: column;
  padding: 10px;
  border: 1px solid black;
  max-width: 250px;
  width: 100%;
  box-sizing: border-box;
  margin-right: 15px;
}

.list .person {
  display: flex;
  padding: 10px;
  border: 1px solid black;
  width: 100%;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  margin-bottom: 10px;
  cursor: pointer;
}
</style>
