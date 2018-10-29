<template>
  <div class="tree-menu">
    <div class="label-wrapper">
      <div :style="indent">
        {{ label }}
      </div>
    </div>
    <div v-if="nodes && nodes.length">
      <ba-ba
        v-for="(node, index) in nodes"
        :key="index"
        :nodes="node.nodes"
        :label="node.label"
        :depth="depth + 1" />
    </div>
    <div v-else />
  </div>
</template>

<script>
export default {
  name: 'AbAb',
  components: {
    BaBa: () => import('@/components/BaBa')
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
