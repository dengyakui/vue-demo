<template>
  <span ref='countup'></span>
</template>

<script>
import CountUp from "countup.js";
var options = {
  useEasing: true,
  useGrouping: true,
  separator: ",",
  decimal: "."
};

export default {
  name: "countup-demo",
  props: {
    autoplay: {
      type: Boolean,
      required: false,
      default: true
    },
    start: {
      type: Number,
      default: 0
    },
    end: {
      type: Number,
      default: 2018
    },
    decimal: {
      type: Number,
      default: 0
    },
    duration: {
      type: Number,
      default: 2.5
    },
    options: {
      type: Object
    }
  },
  data() {
    return {
      counter: null
    };
  },
  methods: {
    initCountUp() {
      this.counter = new CountUp(
        this.$refs.countup,
        this.start,
        this.end,
        this.decimal,
        this.duration,
        this.options
      );
      this.counter.start();
    }
  },
  mounted() {
    this.initCountUp();
  }
};
</script>
