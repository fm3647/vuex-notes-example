<template lang="html">
  <div class="item">
    <div class="meta">
      {{ updated(entity) }}
    </div>
    <div class="content">
      <div class="header">
        {{ header(entity) || '새글쓰기' }}
      </div>
      <div class="extra">
        <Editor v-bind:entity="entity"/>
        {{ words(entity) }}자
        <i class="right floated trash outline icon"
        v-on:click="destroy(entity)"></i>
      </div>
    </div>
  </div>
</template>

<script>
import Editor from './Editor'
import { mapGetters, mapActions } from 'vuex'
export default {
  computed: {
    ...mapGetters([
      'updated',
      'words',
      'header'
    ])
  },
  props: [
    'entity'
  ],
  methods: {
    ...mapActions([
      'destroy'
    ])
  },
  components: {
    Editor
  }
}
</script>

<style lang="css">
</style>
