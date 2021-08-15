<template>
    <li>
  <base-card type="columnContainer">

      <header>
        <h3>{{ title }}</h3>
        <base-button @click="submitDeletedResource" mode="action">Delete</base-button>
      </header>
      <div class="description-container">
        <p>{{ description }}</p>
      </div>

      <nav class="link-container">
        <a target="blank" title="courseLink" :href="link">View Resource</a>
      </nav>
   
  </base-card>
   </li>
</template>

<script>

export default {

  props: ["link", "description", "title","id"],
  inject:["deletedResource"],
  data() {
    return {};
  },
  methods:{
    submitDeletedResource(){

      this.deletedResource(this.id);
    }
  }

};
</script>

<style scoped>
li{
    width:100%;
    margin-bottom:1rem;
}
header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 1rem;
}

div.description-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  padding: 1rem;
  font-family: inherit;
  font-weight: bold;
}
nav.link-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  padding: 1rem;
  justify-content: flex-start;
  align-items: center;
}
a{
    color:rgb(128, 83, 0);
}
nav.link-container a:hover,
nav.link-container a:visited {
  color: rgb(211, 74, 24);
}
/* li {
  display: flex;
  flex-direction: column;
  margin: auto;
  margin-bottom: 1rem;
}
li div.resource-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  box-shadow: 0 2px 10px #ccc;
  border-rad
  justify-content: center;
  width: 500px;
}
header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 1rem;
}
header button {
  color: white;
  border-radius: 2px;
  background-color: rgb(160, 0, 27);
  border: none;
  outline: none;
  padding: 12px 20px;
  font-family: inherit;
  font-weight: bold;
  cursor: pointer;
}
header button:hover {
  background-color: rgb(219, 29, 60);
}
div.description-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  padding: 1rem;
  font-family: inherit;
  font-weight: bold;
}
nav.link-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  padding: 1rem;
  justify-content: flex-start;
  align-items: center;
}
nav.link-container a:hover,
nav.link-container a:visited {
  color: rgb(141, 45, 10);
} */
</style>
