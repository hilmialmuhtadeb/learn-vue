<template>
  <input type="text" :value="txt" @input="changeText">
</template>

<script>
export default {
  props: ['txt'],
  data() {
    return {
      text: '',
    };
  },
  methods: {
    changeText(event) {
      this.text = event.target.value;
      // console.log(this.text);
      this.$emit('textChanged', this.text);
    },
  },
};
</script>
