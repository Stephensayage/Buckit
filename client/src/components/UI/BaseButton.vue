<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode']
};
</script>

<style scoped>
button {
  margin: 0 15px;
  padding: 10px;
  font-family: inherit;
  background-color: rgb(216, 70, 86);
  border: 1px solid rgb(216, 70, 86);
  color: white;
  cursor: pointer;
  outline: none;
}

button:hover,
button:active {
  background-color: rgb(132, 1, 16);
  border-color: rgb(132, 1, 16);
}

.flat {
  background-color: transparent;
  color: rgb(132, 1, 16);
  border: none;
}

.flat:hover,
.flat:active {
  color: white;
  background-color: rgb(132, 1, 16);
  border-radius: 4px;
}
.flat:active {
  box-shadow: 0 1px 2px black;
}
</style>
