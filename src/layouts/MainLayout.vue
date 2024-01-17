<template>
  <div id="grid">
    <LeftSideMenu />
    <MenuOptionName />
    <ListViewer />
    <!-- <FooterFixedInfo />
    <MenuOptionHeader />
    <RouterView />
    <RightSideMenu /> -->
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import LeftSideMenu from '../components/Left-Side-Menu/index.vue';
import MenuOptionName from '../components/Menu-Option-Name/index.vue';
import ListViewer from '../components/List-Viewer/index.vue';

export default defineComponent({
  name: 'MainLayout',
  components: { LeftSideMenu, MenuOptionName, ListViewer },
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
#grid {
  display: grid;
  height: 100vh;
  grid-template-columns: 71px 240px auto 240px;
  grid-template-rows: 46px auto 52px;
  grid-template-areas:
    'SL SN CI CI'
    'SL CL CD UL'
    'SL UI CD UL';
}
</style>
