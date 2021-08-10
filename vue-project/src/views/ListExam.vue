<template>
  <table>
    <thead>
      <tr>
        <th>도시명</th>
        <th>시구군</th>
      </tr>
    </thead>
    <tbody>
      <tr v-bind:key="i" v-for="(item, i) in list">
        <td>{{ item.city }}</td>
        <td>{{ item.sigugun }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      list: [
        { city: "인천", sigugun: "계양구" },
        { city: "인천", sigugun: "서구" },
        { city: "인천", sigugun: "미추홀구" },
        { city: "서울", sigugun: "양천구" },
      ],
    };
  },
  async mounted() {
    const result = await axios.get("http://localhost:3000");
    this.list = result.data;
  },
};
</script>