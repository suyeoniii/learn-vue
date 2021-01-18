<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <input type="text" v-model="input" />
    <button type="button" @click="setData">set</button>
    <button type="button" @click="getData">button</button>

    <select class="form-control" v-model="region" @change="changeRegion">
      <option :key="i" :value="d.v" v-for="(d, i) in options">{{ d.t }}</option>
    </select>

    <!-- 유사한걸로 v-show 잇는데 얘는 일단 렌더링하고 안보여주는거, v-if는 렌더링을 아에 안함 -->
    <table class="table table-bordered" v-if="tableShow">
      <tr :key="i" v-for="(d, i) in options">
        <td>{{ d.v }}</td>
        <td>{{ d.t }}</td>
      </tr>
    </table>
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
      tableShow: false,
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
    changeRegion() {
      alert(this.region);
    },
  },
};
</script>
