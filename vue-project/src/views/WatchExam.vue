<template>
  <h1>{{ fullName }}</h1>
  <button type="button" @click="changeFirstName">이름변경</button>
</template>

<script>
export default {
  data() {
    return {
      firstName: "hyugwoo",
      lastName: "An",
      fullName: "",
    };
  },
  watch: {
    firstName() {
      this.fullName = this.firstName + " " + this.lastName;
    },
    lastName() {
      this.fullName = this.firstName + " " + this.lastName;
    },
  },
  method: {
    changeFirstName() {
      this.firstName = "hyungwoo";
    },
  },
};
</script>