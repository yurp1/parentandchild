<template>
  <div class="parent-component">
    <h1>Parent Component</h1>
    <child-component @sendData="displayData">
      <template v-slot:default>
        <p>Data dari slot parent.</p>
      </template>
    </child-component>
    <p>{{ parentData }}</p>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      parentData: ''
    };
  },
  methods: {
    displayData(data) {
      this.parentData = data;
    }
  }
};
</script>

<style scoped>
.parent-component {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #333;
  margin-bottom: 20px;
}

p {
  color: #666;
  margin-top: 10px;
}
</style>
