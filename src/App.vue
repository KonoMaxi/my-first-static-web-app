<template>
  <ul>
    <li>Hello {{ value }}</li>
    <li>{{ message }}</li>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World",
      message: ""
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    this.message = text;
  }
};
</script>
