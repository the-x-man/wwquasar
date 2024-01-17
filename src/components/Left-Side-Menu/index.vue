<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <MenuOption isHome />
    <div class="separator"></div>
    <MenuOption :mentions="27890" />
    <MenuOption :mentions="20" />
    <MenuOption :mentions="5" />
    <MenuOption />
    <MenuOption :mentions="5" />
    <MenuOption :mentions="3" />
    <MenuOption />
    <div class="separator"></div>
    <MenuOption :mentions="27890" />
    <MenuOption :mentions="20" />
    <MenuOption :mentions="5" />
    <MenuOption />
    <MenuOption :mentions="5" />
    <MenuOption :mentions="3" />
    <MenuOption />
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
import MenuOption from './MenuOption.vue';

export default defineComponent({
  name: 'LeftSideMenu',
  components: {
    MenuOption,
  },
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  grid-area: SL;
  background: var(--tertiary);
  padding: 11px 0;
  max-height: 100vh;
  overflow-y: scroll;
  &::-webkit-scrollbar {
    display: none;
  }
}

.separator {
  width: 32px;
  margin-bottom: 8px;
  border-bottom: 2px solid var(--quaternary);
}
</style>
