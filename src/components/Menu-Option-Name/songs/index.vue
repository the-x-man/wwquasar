<template>
  <div class="container">
    <div class="title">{{ $t('general.song') }}</div>
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
      <q-btn
        flat
        square
        unelevated
        dense
        icon="add_box"
        @click="addmodal = true"
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
            ><span class="text-weight-bold">Worship Neo</span> Song
            Search</q-toolbar-title
          >
          <q-btn flat round dense icon="close" v-close-popup />
        </q-toolbar>
        <q-card-section>
          <div class="row">
            <div class="col-12 col-md-8">
              <q-input
                square
                outlined
                v-model="text"
                dark
                :label="$t('songs.searchcaption')"
              />
            </div>
            <div class="col-12 col-md-4">
              <q-toggle
                color="blue"
                dark
                v-model="toggleremotesearch"
                size="xl"
                :label="$t('songs.togglesearch')"
              />
            </div>
          </div>
          <div class="row">
            <div class="q-pa-md text-white col-12 col-md-4">
              <q-scroll-area
                style="height: 65vh; max-width: 25vw"
                :content-style="{ backgroundColor: '#292b2f' }"
              >
                <q-item clickable v-ripple="false" v-for="n in 100" :key="n">
                  <q-item-section
                    >Song title with a maximum number of words as
                    possible</q-item-section
                  >
                </q-item>
              </q-scroll-area>
              <br />
              <q-btn
                color="secondary"
                unelevated
                square
                :ripple="false"
                icon="add"
                :label="$t('songs.formaddnewsong')"
              />
            </div>
            <div class="q-pa-md text-white col-12 col-md-6">
              <q-input
                square
                outlined
                v-model="songtitle"
                dark
                stack-label
                color="white"
                disable
                :label="$t('songs.formtitle')"
              />
              <br />
              <q-separator />
              <q-input
                v-model="text"
                filled
                type="textarea"
                disable
                stack-label
                dark
                :label="$t('songs.formlyrics')"
              />
              <br />
              <q-separator />
              <q-btn
                color="primary"
                unelevated
                square
                :ripple="false"
                :label="$t('songs.formselect')"
                @click="toggleSearch"
              />
            </div>
          </div>
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'SongMenuBar',
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
