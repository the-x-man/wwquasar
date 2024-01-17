<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <div class="category">
      <div class="">Recent Songs</div>
      <div class="category-icon">
        <AddCategoryIcon :size="21" />
      </div>
    </div>
    <ListItemButton channelName="Bem-Vindo" />
    <ListItemButton channelName="REGRAS" />
    <ListItemButton channelName="Informações" />
    <ListItemButton selected channelName="sala-01" />
    <ListItemButton channelName="sala-02" />
    <ListItemButton channelName="sala-03" />
    <ListItemButton channelName="Bem-Vindo" />
    <ListItemButton channelName="REGRAS" />
    <ListItemButton channelName="Informações" />
    <ListItemButton channelName="sala-02" />
    <ListItemButton channelName="sala-03" />
    <ListItemButton channelName="Bem-Vindo" />
    <ListItemButton channelName="REGRAS" />
    <ListItemButton channelName="Informações" />
    <ListItemButton channelName="sala-02" />
    <ListItemButton channelName="sala-03" />
    <ListItemButton channelName="Bem-Vindo" />
    <ListItemButton channelName="REGRAS" />
    <ListItemButton channelName="Informações" />
    <ListItemButton channelName="sala-02" />
    <ListItemButton channelName="sala-03" />
    <ListItemButton channelName="Bem-Vindo" />
    <ListItemButton channelName="REGRAS" />
    <ListItemButton channelName="Informações" />
    <div class="category">
      <div class="">Recent Songs</div>
      <div class="category-icon">
        <AddCategoryIcon :size="21" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import ListItemButton from './ListItemButton.vue';

export default defineComponent({
  name: 'ListViewer',
  components: { ListItemButton },
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
.container {
  grid-area: CL;
  display: flex;
  flex-direction: column;
  padding: 24px 10px 0 16px;
  background: var(--secondary);
  height: 100%;
  overflow: scroll;
  &::-webkit-scrollbar {
    display: none;
  }
}

.category {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 6px;
  color: var(--grey);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  .category-icon {
    color: var(--symbol);
    cursor: pointer;
  }
}
</style>
