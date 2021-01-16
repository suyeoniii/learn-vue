<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <input type="text" v-model="input" />
    <button type="button" @click="setData">set</button>
    <button type="button" @click="getData">button</button>

    <select class="form-control" v-model="region">
      <option :key="i" value="d.v" v-for="(d, i) in options">{{ d.t }}</option>
    </select>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "subari",
      input: "text",
      options: [
        { v: "S", t: "Seoul" },
        { v: "J", t: "Jeju" },
        { v: "B", t: "Busan" },
      ],
      region: "J",
    };
  },
  watch: {
    input() {
      console.log(this.input);
    },
  },
  methods: {
    getData() {
      alert(this.input);
    },
    setData() {
      this.input = "data";
    },
  },
};
</script>
