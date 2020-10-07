<template>
  <div class="form-ctn">
    <base-card>
      <form>
        <div class="form">
          <label>Title</label>
          <input id="title" name="title" type="text" />
        </div>
        <div class="form">
          <label>Description</label>
          <textarea id="description" name="description" rows="3"></textarea>
        </div>
        <div class="form">
          <label>Link</label>
          <input id="link" name="link" type="url" />
        </div>
        <div>
          <base-button type="submit" mode="submit">Submit</base-button>
        </div>
      </form>
    </base-card>
  </div>
</template>

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
