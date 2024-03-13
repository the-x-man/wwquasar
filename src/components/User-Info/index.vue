<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container">
    <div class="profile">
      <q-card dark class="apply-dark" square flat>
        <q-tabs
          v-model="tab"
          dense
          narrow-indicator
          no-caps
          class="text-white apply-dark"
        >
          <q-tab class="text-blue" name="house" label="House" />
          <q-tab class="text-blue" name="stage" label="Stage" />
        </q-tabs>
        <q-separator />
        <q-tab-panels v-model="tab" animated dark class="apply-dark">
          <q-tab-panel name="house">
            <!-- <div class="text-h6">Mails</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. -->
            <div class="video-previewer" />
          </q-tab-panel>

          <q-tab-panel name="stage">
            <div class="text-h6">Alarms</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'UserInfo',
  components: {},
  setup() {
    return {
      tab: ref('house'),
    };
  },
});
</script>
<style lang="scss" scoped>
.container {
  grid-area: UI;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: start;
  padding: 10px;
  background: var(--quaternary);
  box-shadow: rgba(0, 0, 0, 0.2) 0 1px 0 0;
}
.profile {
  display: flex;
  align-items: center;
}

.avatar {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: var(--grey);
}

.userdata {
  display: flex;
  flex-direction: column;
  margin-left: 8px;
  font-size: 13px;
  strong {
    display: block;
    color: var(--white);
  }

  span {
    color: var(--grey);
  }
}

.actions {
  color: var(--grey);
  span {
    cursor: pointer;
    transition: 0.2s;
    &:hover {
      color: var(--white);
    }
  }
}

.apply-dark {
  background-color: var(--primary);
}

.video-previewer {
  min-width: 100%;
  min-height: 100%;

  width: 100%;
  height: auto;
}
</style>
