<template>
  <section class="container">
    <div>
      <ab-ab
        :nodes="tree.nodes"
        :depth="0"
        :label="tree.label" />
    </div>
  </section>
</template>

<script>
import AbAb from '~/components/AbAb.vue'

const tree = {
  label: 'root',
  nodes: [
    {
      label: 'item1',
      nodes: [
        {
          label: 'item1.1'
        },
        {
          label: 'item1.2',
          nodes: [
            {
              label: 'item1.2.1'
            }
          ]
        }
      ]
    },
    {
      label: 'item2'
    }
  ]
}

export default {
  components: {
    AbAb
  },
  data () {
    return {
      tree
    }
  }
}
</script>
