<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container-flex" :class="{ active: selected }">
    <div class="channel-info">
      <HashTagIcon class="hash-icon" :size="20" />
      <div class="hash-icon">{{ channelName }}</div>
    </div>
    <div class="channel-actions">
      <InvicteIcon class="icon-actions" :size="16" />
      <SettingIcon class="icon-actions" :size="16" />
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ListViewer',
  components: {},
  props: {
    channelName: String,
    selected: Boolean,
  },
  setup() {
    return {};
  },
});
</script>
<style scoped lang="scss">
.container-flex {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  padding: 5px 3px;
  border-radius: 5px;

  > div {
    display: flex;
    align-items: center;
  }

  .channel-info {
    div {
      color: var(--senary);
      margin-left: 5px;
    }
    .hash-icon {
      color: var(--symbol);
      font-size: 12px;
    }
  }

  .channel-actions {
    display: none;
    .icon-actions {
      color: var(--symbol);
      margin-left: 4px;
      &:hover {
        color: var(--white);
      }
    }
  }
  &:hover,
  &.active {
    background: var(--quinary);
    .channel-info {
      div {
        color: var(--white);
      }
    }
    .channel-actions {
      display: flex;
    }
  }
}
</style>
