<template>
  <div
    class="MenuButton"
    :class="{
      'MenuButton-isHome': isHome,
      'MenuButton-hasNotification': hasNotification,
    }"
  >
    <!-- <img src="../../../dist/discord.svg" alt="discord" v-if="isHome"> -->
    <div class="mentions" v-if="mentions">
      {{ formattedCount }}
    </div>
  </div>
</template>
<script>
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'MenuOption',
  components: {},
  props: {
    selected: Boolean,
    isHome: Boolean,
    hasNotification: Boolean,
    mentions: Number,
  },
  computed: {
    formattedCount() {
      if (this.mentions < 1000) {
        return this.mentions.toFixed(0); // assuming an integer
      } else {
        const s = (0.1 * Math.floor(this.mentions / 100)).toFixed(1);
        return s.replace('.0', '') + 'K';
      }
    },
  },
});
</script>
<style lang="scss" scoped>
.MenuButton {
  display: flex;
  flex-shrink: 0;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  margin-bottom: 8px;
  background: var(--primary);
  cursor: pointer;
  position: relative;
  border-radius: 50%;
  transition: 0.2s;
  &:hover,
  &.active {
    background: var(--discord);
    border-radius: 25%;
  }

  img {
    width: 24px;
    color: var(--white);
  }

  .mentions {
    background: var(--notification);
    width: auto;
    height: 20px;
    padding: 0 4px;
    position: absolute;
    bottom: -8px;
    right: -10px;
    border-radius: 12px;
    text-align: center;
    font-size: 10px;
    font-weight: bold;
    color: var(--white);
    border: solid 4px var(--quaternary);
  }
}

.MenuButton-hasNotification {
  &::before {
    content: '';
    width: 9px;
    height: 9px;
    background: var(--white);
    position: absolute;
    left: -17px;
    top: calc(50% - 4.5px);
    border-radius: 50%;
    display: block;
  }
}

.MenuButton-isHome {
  background: var(--link);
  &.active,
  &:hover {
    border-radius: 16px;
    background-color: var(--link);
  }
}
</style>
