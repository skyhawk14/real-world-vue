<template>
  <div class="icon-wrapper">
    <svg class="icon" :width="width" :height="height" v-html="svg"></svg>
    <slot name="details"></slot>
  </div>
</template>

<script>
import feather from 'feather-icons'
export default {
  props: {
    iconName: String,
    width: {
      type: [Number, String],
      default: 24,
    },
    height: {
      type: [Number, String],
      default: 24,
    },
  },
  computed: {
    svg() {
      return feather.icons[this.iconName].toSvg({
        class: 'icon',
        width: this.width,
        height: this.height,
      })
    },
  },
}
</script>

<style scoped>
.icon-wrapper {
  display: inline-flex;
  align-items: center;
  color: rgba(0, 0, 0, 0.4);
  font-size: 1rem;
  font-weight: 600;
}
.icon {
  stroke: currentColor;
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  fill: none;
  margin-right: 6px;
}
</style>
