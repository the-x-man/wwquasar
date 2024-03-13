<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <!-- <SongMenuBar /> -->
  <ScriptureMenuBar />
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import SongMenuBar from './songs/index.vue';
import ScriptureMenuBar from './bible/index.vue';

export default defineComponent({
  name: 'MenuOptionName',
  // eslint-disable-next-line vue/no-unused-components
  components: { SongMenuBar, ScriptureMenuBar },
  setup() {
    return {};
  },
  methods: {},
});
</script>
<style scoped lang="scss"></style>
