<template>
  <div class="about">
    <h1 :style="{fontSize: `${fontSize}em`}">{{ text }}</h1>
    <resize-button :qty="1" @resizeFont="resizeFontSize($event)">Perbesar</resize-button>
    <resize-button :qty="0.5" :smaller="true" @resizeFont="resizeFontSize($event)">Perkecil</resize-button>
    <div style="margin: 20px;">
      <live-text :txt="text" @textChanged="text = $event"></live-text>
    </div>
  </div>
</template>

<script>
import VueNumeric from 'vue-numeric';
import LiveText from '../components/LiveText.vue';
import ResizeButton from '../components/ResizeButton.vue';

export default {
  components: {
    VueNumeric,
    'live-text': LiveText,
    'resize-button': ResizeButton,
  },
  data() {
    return {
      fontSize: 1,
      text: 'Luar Biasa',
    };
  },
  methods: {
    resizeFontSize(args) {
      const { qty, smaller } = args;
      if (!smaller) {
        this.fontSize += qty;
      } else {
        this.fontSize -= qty;
      }
    },
  },
};
</script>
