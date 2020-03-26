<template>
  <div class="hello"></div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      firstArray: [{ path: "/a/b/c" }, { path: "/5/6/7" }, { path: "/6/a/a" }],
      string: "/a/b/c"
    };
  },
  beforeMount() {
    this.findValue(this.firstArray, this.string);
  },
  methods: {
      findValue(o, value) {
    console.log(o, value)
    for (var prop in o) {
        if (o.hasOwnProperty(prop) && o[prop] === value) {
            return prop;
        }
    }
    return null;
  }
  }
};
</script>

<style scoped>
</style>
