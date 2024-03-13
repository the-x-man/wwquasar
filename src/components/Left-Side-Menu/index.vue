<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <!-- <MenuOption :menuitem="1" />
    <div class="separator"></div> -->
    <MenuOption :mentions="27890" :menuitem="2" />
    <MenuOption :mentions="10" :menuitem="4" />
    <MenuOption :mentions="20" :menuitem="3" />
    <MenuOption :menuitem="5" />
    <MenuOption :menuitem="6" />
    <MenuOption :menuitem="7" />
    <MenuOption :menuitem="10" />
    <div class="separator"></div>
    <MenuOption :menuitem="8" />
    <MenuOption :menuitem="9" />
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
