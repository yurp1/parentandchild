<template>
  <div class="child-component">
    <h2>Child Component</h2>
    <button @click="emitData">Kirim Data ke Parent</button>
    <grand-child-component @sendData="emitDataToParent">
      <template v-slot:default>
        <p>Data dari slot child.</p>
      </template>
    </grand-child-component>
    <slot></slot>
  </div>
</template>

<script>
import GrandChildComponent from './GrandChildComponent.vue';

export default {
  components: {
    GrandChildComponent
  },
  methods: {
    emitData() {
      this.$emit('sendData', 'Data dari Child Component');
    },
    emitDataToParent(data) {
      this.$emit('sendData', data);
    }
  }
};
</script>

<style scoped>
.child-component {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}

h2 {
  color: #333;
  margin-bottom: 10px;
}

button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #45a049;
}

p {
  color: #666;
  margin-top: 10px;
}
</style>
