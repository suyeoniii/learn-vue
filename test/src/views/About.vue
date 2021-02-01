<template>
  <div>
    <h1>About {{ name }}</h1>
    <input type="text" v-model="input" />
    <button type="button" @click="getData">get</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "subari",
      input: "text",
    };
  },
  methods: {
    getData() {
      alert(this.input);
    },
  },
};
</script>
