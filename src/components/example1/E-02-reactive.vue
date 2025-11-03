<template>
  <div>{{ fullName }}</div>
</template>

<script>
export default {
  name: "E02Reactive",
  data() {
    return {
      firstName: "Donghun",
      lastName: "Kim"
    };
  },
  mounted() {

    console.log('mounted');

    let a = 10;

    setTimeout(() => {
      a = 20;
      console.log(a);
    }, 500);
    setTimeout(() => {
      this.lastName = "123";
    }, 1000);

    setTimeout(() => {
      this.firstName = "KDH";
    }, 2000);
  },
  computed: {
    fullName() {
      return this.firstName + " " + this.lastName;
    }
  }
};
</script>
