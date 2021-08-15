<template>
  <base-card type="rowContainer">
    <base-button
      :mode="addResourceButton"
      @click="setSelectedTab('add-resource')"
      >Add Resource</base-button
    >
    <base-button
      :mode="storeResourceButton"
      @click="setSelectedTab('stored-resource')"
      >Stored Resources</base-button
    >
  </base-card>

  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResource from "./StoredResources.vue";
import AddResource from "./AddResources.vue";

export default {
  components: {
    StoredResource,
    AddResource,
  },
  data() {
    return {
      selectedTab: "storedResources",
      storedResources: [
        {
          id: "Official-guide",
          title: "Official Guide",
          description: "Learning the vue js from scratch",
          link: "https://www.vuejs.org",
        },
        {
          id: "Learning new",
          title: "Google",
          description: "Learning the vue js from google",
          link: "https://www.google.com",
        },
      ],
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addNewResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString,
        title: title,
        description: description,
        link: link,
      };

      this.storedResources.unshift(newResource);
      this.selectedTab = "stored-resource";
    },
    deleteResource(ResourceId) {
      const resFound = this.storedResources.filter(
        (res) => res.id === ResourceId
      );
      console.log(resFound);
      const resIndex = this.storedResources.findIndex(
        (res) => res.id === ResourceId
      );
      this.storedResources.splice(resIndex, 1);
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      newResource: this.addNewResource,
      deletedResource: this.deleteResource,
    };
  },
  computed: {
    addResourceButton() {
      return this.selectedTab === "add-resource" ? "action" : null;
    },
    storeResourceButton() {
      return this.selectedTab === "stored-resource" ? "action" : null;
    },
  },
};
</script>

<style scoped>
div.button-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  padding: 2rem;
  justify-content: center;
  align-items: center;
}
</style>
