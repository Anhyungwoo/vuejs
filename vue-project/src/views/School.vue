<template>
  <h1>School.vue</h1>
  <h2 @click="changeTitle">{{ title }}</h2>
  <SchoolTitle />
  <school-title />
  <input type="checkbox" />
  <select v-model="selectedCity">
    <option value="인천">인천</option>
    <option value="서울">서울</option>
    <option value="경기">경기</option>

    <button type="button"
  </select>
</template>

<script>
import SchoolTitle from "../components/SchoolTitle.vue";
export default {
  components: { SchoolTitle },
  data() {
    return {
      style1 : "width : 100px",
      style2 : "height : 100px",
      style3 : "backgroundColor:blue",
      styleobject : {
        color : "red",
        width : "100px",
        height : "100px",
        backgroundColor : "orange"

      }
      title: "학교 홈페이지",
      
    };
  },
  created() {
    console.log("Created");
  },
  mounted() {
    console.log("Mounted");
  },
  unmounted() {
    console.log("Unmounted");
  },
  methods: {
    changeTitle() {
      this.changeTitle2();
    },
    changeTitle2() {
      this.title = "(변경)학교 홈페이지";
    },
  },
};
</script>