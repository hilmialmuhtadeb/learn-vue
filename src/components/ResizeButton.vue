<template>
  <button @click="$emit('resizeFont', {qty, smaller})">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    qty: Number,
    smaller: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
