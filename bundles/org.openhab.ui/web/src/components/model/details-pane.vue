<template>
  <div>
    <item-state-preview v-if="model.item.created !== false" :item="model.item" :context="context" />

    <f7-block-title>Item</f7-block-title>
    <item-details :model="model" :links="links" @item-updated="$emit('item-updated')" @item-created="$emit('item-created')" @item-removed="$emit('item-removed')" @cancel-create="$emit('cancel-create')" />
    <f7-block-title v-if="model.item.type !== 'Group' && model.item.created !== false">Channel Links</f7-block-title>
    <link-details :item="model.item" :links="links" />
  </div>
</template>

<script>
import ItemStatePreview from '@/components/item/item-state-preview.vue'
import ItemDetails from '@/components/model/item-details.vue'
import LinkDetails from '@/components/model/link-details.vue'

export default {
  props: ['model', 'links', 'context'],
  components: {
    ItemStatePreview,
    ItemDetails,
    LinkDetails
  },
  methods: {
  }
}
</script>
