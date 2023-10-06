<template>
  <div class="tags-list">
    <div
      :class="{ isPreview: isPreview }"
      class="tag-item"
      v-for="(tag, index) in tags"
      :key="index"
      @click="handleAddTag"
    >
      {{ tag }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tags: {
      type: Array,
      required: true
    },
    isPreview: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      tagsActive: []
    }
  },
  methods: {
    handleAddTag(event) {
      event.target.classList.toggle('isActive')
      if (event.srcElement.className == 'tag-item isActive') {
        this.tagsActive.push(event.srcElement.innerText)
      } else {
        this.tagsActive = this.tagsActive.filter(
          elem => elem != event.srcElement.innerText
        )
      }
      this.$emit('onStoreTag', this.tagsActive)
    }
  }
}
</script>
