<template>
  <div class="grand-child-component">
    <h3>Grand Child Component</h3>
    <button @click="emitData">Kirim Data ke Child</button>
    <slot></slot>
  </div>
</template>

<script>
export default {
  methods: {
    emitData() {
      this.$emit('sendData', 'Data dari Grand Child Component');
    }
  }
};
</script>

<style scoped>
.grand-child-component {
  background-color: #fafafa;
  padding: 15px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 15px;
}

h3 {
  color: #333;
  margin-bottom: 8px;
}

button {
  background-color: #2196f3;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #0b7dda;
}

p {
  color: #666;
  margin-top: 10px;
}
</style>
