<template>
  <div id="grid">
    <LeftSideMenu />
    <MenuOptionName />
    <ListViewer />
    <UserInfo />
    <PageInfo />
    <MainContent />
    <RightSidePanel />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import LeftSideMenu from '../components/Left-Side-Menu/index.vue';
import MenuOptionName from '../components/Menu-Option-Name/index.vue';
import ListViewer from '../components/List-Viewer/index.vue';
import UserInfo from '../components/User-Info/index.vue';
import PageInfo from '../components/Page-Info/index.vue';
import MainContent from '../components/Main-Content/index.vue';
import RightSidePanel from '../components/Right-Side-Panel/index.vue';

export default defineComponent({
  name: 'MainLayout',
  components: {
    LeftSideMenu,
    MenuOptionName,
    ListViewer,
    UserInfo,
    PageInfo,
    MainContent,
    RightSidePanel,
  },
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
#grid {
  display: grid;
  height: 100vh;
  grid-template-columns: 75px 20% auto 20%;
  grid-template-rows: 46px auto 250px;
  grid-template-areas:
    'SL SN CI CI'
    'SL CL CD UL'
    'SL UI CD UL';
}
</style>
