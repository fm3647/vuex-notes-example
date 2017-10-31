<template lang="html">
  <div class="ui container notes">
    <h4 class="ui horizontal divider header">
      <i class="paw icon"></i>
      Suuon Notes App _ Vue.js
    </h4>
    <a href="" class="ui right floated basic violet button" v-on:click="create">글쓰기</a>
    <div class="ui divided items">
      <note
        v-for="entity in entities"
        v-bind:entity="entity">
      </note>
      <span
        class="ui small disabled header"
        v-if="!entities.length">
        작성글이 없네요, 글쓰기를 클릭하시면 내용입력을 할 수 있습니다.</span>
    </div>
  </div>
</template>

<script>
import Note from './Note'
import { mapGetters, mapActions } from 'vuex'

export default {
  created () {
    this.initial()
  },
  methods: {
    ...mapActions([
      'initial',
      'create'
    ])
  },
  computed: {
    ...mapGetters([
      'entities'
    ])
  },
  components: {
    Note
  }
}
</script>

<style lang="css">
</style>
