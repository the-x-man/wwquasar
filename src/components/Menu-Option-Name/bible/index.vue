<template>
  <div class="container">
    <div class="title">{{ $t('general.bible') }}</div>
    <div class="icon">
      <q-btn
        flat
        dense
        square
        unelevated
        outline
        icon="search"
        :ripple="false"
        @click="searchmodal = true"
      />
    </div>
    <q-dialog
      v-model="searchmodal"
      dark
      persistent
      maximized
      class="apply-dark"
      transition-show="fade"
    >
      <q-card class="apply-dark">
        <q-toolbar>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo.svg" />
          </q-avatar>

          <q-toolbar-title
            ><span class="text-weight-bold">Worship Neo</span> Scripture
            Search</q-toolbar-title
          >
          <q-btn flat round dense icon="close" v-close-popup />
        </q-toolbar>
        <q-card-section>
          <div class="row"></div>
          <div class="row"></div>
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'ScriptureMenuBar',
  components: {},
  setup() {
    return {
      searchmodal: ref(false),
      addmodal: ref(false),
      toggleremotesearch: ref(false),
      text: ref(null),
      songtitle: ref(null),
    };
  },
  methods: {
    toggleSearch() {
      this.searchmodal = !this.searchmodal;
    },
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
.cursor-pointer {
  cursor: pointer;
}
.apply-dark {
  background-color: var(--primary);
  color: var(--grey);
}
</style>
