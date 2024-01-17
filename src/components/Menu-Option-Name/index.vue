<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <div class="title">Song Lyrics</div>
    <div class="icon">
      <q-icon size="1.5em" name="font_download" />
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MenuOptionName',
  components: {},
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
.container {
  grid-area: SN;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: var(--secondary);
  padding: 0 11px 0 16px;
  box-shadow: rgba(0, 0, 0, 0.8) 1px 0 0;
  z-index: 2;
}
.title {
  color: var(--white);
  font-size: 16px;
  font-weight: bold;
}

.icon {
  color: var(--white);
}
</style>
