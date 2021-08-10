<template>
  <h1>{{ fullName }}</h1>
</template>
<script>
import { computed } from '@vue/runtime-core';
export default {
  data() {
    return {
      firstName : "hyungwoo",
      lastName : "An"
    }
  }
  computed :  {
    fullName() {
      return this.lastName + " " + this.firstName;
    }
  }
}
</script>