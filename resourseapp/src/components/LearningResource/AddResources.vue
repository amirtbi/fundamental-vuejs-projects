<template>
  <section>
    <base-card type="columnContainer">
      <div class="title-container">
        <h2>Add New Resource</h2>
      </div>
      <form class="form-control" @submit.prevent="submitNewResource">
        <div class="form-control__field">
          <label for="title">Title</label>
          <input type="text" id="title" name="title" ref="titleInput" />
        </div>
        <div class="form-control__field">
          <label for="description">Description</label>
          <textarea
            rows="3"
            ref="descInput"
            id="description"
            name="description"
            resize="none"
          ></textarea>
        </div>
        <div class="form-control__field">
          <label for="link">Link</label>
          <input ref="linkInput" type="url" id="link" name="link" />
        </div>
        <div class="form-control__field">
          <base-button mode="action" type="submit">ADD RESOURCE</base-button>
        </div>
      </form>
    </base-card>
    <teleport to="body">
      <base-modal v-if="modalAndBackDropIsDisplayed" title="Invalid inputs">
      
        <template #description>
          <p class="error-description">Please fill the blanks</p>
          <p class="error-description">Please make sure that all inputs are valid and entere valid a few characters.!</p>
        </template>
      </base-modal>

    </teleport>
  </section>
</template>

<script>
export default {
  inject: ["newResource"],
  components: {},
  data() {
    return {
      modalAndBackDropIsDisplayed: false,
      inputsAreInvalid: false,
    };
  },
  provide() {
    return {
      hideModal: this.closeHandler,
    };
  },
  methods: {
    submitNewResource() {
      const titleInput = this.$refs.titleInput.value;
      const linkInput = this.$refs.linkInput.value;
      const descInput = this.$refs.descInput.value;

      this.inputsAreInvalid =
        titleInput.trim() === "" ||
        linkInput.trim() === "" ||
        descInput.trim() === "";
      if (this.inputsAreInvalid) {
        this.modalAndBackDropIsDisplayed = true;
      }
      if (!this.inputsAreInvalid) {
        this.newResource(titleInput, descInput, linkInput);
      }
    },
    closeHandler() {
      this.modalAndBackDropIsDisplayed = false;
    },
  },
};
</script>

<style scoped>
.form-control {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 2rem;
}
section {
  margin-top: 4rem;
}
textarea {
  resize: none;
}
div.title-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: center;
  align-items: center;
  color: white;
  background: rgb(17, 0, 80);
}
div.form-control__field {
  display: flex;
  flex-direction: column;
  width: 100%;
  align-items: flex-start;
  justify-content: center;
  margin: 0.5rem;
}
div.form-control__field input,
div.form-control__field textarea {
  width: 100%;
  padding: 10px 12px;
  outline: none;
  border: 1px solid black;
}
div.form-control__field input:focus,
div.form-control__field textarea:focus {
  border: 1px solid rgb(6, 11, 255) !important;
}
label {
  font-weight: bold;
  font-family: inherit;
  font-size: 1.2rem;
  margin-bottom: 10px;
}
#error-title {
  font-family: sans-serif;
  padding-bottom: 0;
  margin-bottom: 0;
}
p.error-description {
  font-family: sans-serif;
  font-weight: bold;
  font-size: 1.5rem;
  margin:0;
  padding: 10px;
}
</style>
