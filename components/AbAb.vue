<template>
  <div class="tree-menu">
    <div class="label-wrapper">
      <div :style="indent">
        <i
          v-if="nodes"
          class="fa" />
        {{ label }}
      </div>
    </div>
    <ba-ba
      v-for="(node, index) in nodes"
      :key="index"
      :nodes="node.nodes"
      :label="node.label"
      :depth="depth + 1" />
  </div>
</template>

<script>
import BaBa from '@/components/BaBa'

export default {
  name: 'AbAb',
  components: {
    BaBa
  },
  props: [
    'nodes',
    'label',
    'depth'
  ],
  computed: {
    indent() {
      return { transform: `translate(${this.depth * 50}px)` }
    }
  }
}
</script>
