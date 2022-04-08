<template>
  <div class="content">
    <div class="info">
      <div class="line">Name: {{ person.name }}</div>
      <div class="line">Phone: {{ person.phone }}</div>
      <div class="line">Email: {{ person.email }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PersonComponent",
  props: {
    person: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.info {
  display: flex;
  flex-direction: column;
  padding: 10px;
  border: 1px solid black;
  max-width: 250px;
  width: 100%;
  box-sizing: border-box;
}

.list .line {
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
