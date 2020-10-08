<template>
  <div class="form-ctn">
    <base-dialog
      v-if="inputIsInvalid"
      title="Invalid User Input"
      @close="closeDialog"
    >
      <template #default>
        <p>At Least One Input Value is Invalid</p>
        <p>Please Check All Input Fields</p>
      </template>
      <template #actions>
        <base-button @click="closeDialog">X</base-button>
      </template>
    </base-dialog>
    <base-card>
      <form @submit.prevent="submitForm">
        <div class="form">
          <label>Title</label>
          <input id="title" name="title" type="text" ref="titleData" />
        </div>
        <div class="form">
          <label>Description</label>
          <textarea
            id="description"
            name="description"
            rows="3"
            ref="descData"
          ></textarea>
        </div>
        <div class="form">
          <label>Link</label>
          <input id="link" name="link" type="url" ref="linkData" />
        </div>
        <div>
          <base-button type="submit" mode="submit">Submit</base-button>
        </div>
      </form>
    </base-card>
  </div>
</template>

<script>
export default {
  inject: { addResource: 'addResource' },
  data() {
    return {
      inputIsInvalid: false
    };
  },
  methods: {
    submitForm() {
      const enteredTitle = this.$refs.titleData.value;
      const enteredDesc = this.$refs.descData.value;
      const enteredLink = this.$refs.linkData.value;

      if (
        enteredTitle.trim() === '' ||
        enteredDesc.trim() === '' ||
        enteredLink.trim() === ''
      ) {
        this.inputIsInvalid = true;
        return;
      }

      this.addResource(enteredTitle, enteredDesc, enteredLink);
      this.$refs.titleData.value = '';
      this.$refs.descData.value = '';
      this.$refs.linkData.value = '';
    },
    closeDialog() {
      this.inputIsInvalid = false;
    }
  }
};
</script>

<style scoped>
label {
  padding: 15px;
  font-weight: bold;
  display: block;
  margin-bottom: 8px;
}

input,
textarea {
  margin: 15px;
  display: block;
  width: 90%;
  font: inherit;
  padding: 2px;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: rgb(207, 204, 198);
  background-color: rgb(210, 207, 201);
}
.form-ctn {
  width: 50%;
}
.form {
  margin: 5px 0;
}
</style>
