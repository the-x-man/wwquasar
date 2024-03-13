<template>
  <div
    class="MenuButton"
    :class="{
      'MenuButton-isHome': isHome,
      'MenuButton-hasNotification': hasNotification,
    }"
  >
    <img :src="svgurl" alt="discord" />
    <div class="mentions" v-if="mentions" alt="discord">
      {{ formattedCount }}
    </div>
    <q-tooltip
      anchor="center right"
      self="center left"
      :offset="[10, 10]"
      class="bg-indigo"
    >
      <strong>{{ $t(tooltip) }}</strong>
    </q-tooltip>
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
    menuitem: Number,
  },
  methods: {
    sortmenu() {
      console.log(menuitem);
    },
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
    svgurl() {
      return `/menu/${this.menuitem}.svg`;
    },
    tooltip() {
      switch (this.menuitem) {
        case 2:
          return 'general.cuelist';
        case 3:
          return 'general.bible';
        case 4:
          return 'general.song';
        case 5:
          return 'general.timer';
        case 6:
          return 'general.image';
        case 7:
          return 'general.video';
        case 10:
          return 'general.slides';
        case 8:
          return 'general.settings';
        case 9:
          return 'general.about';
        default:
          return '';
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
  width: 60px;
  height: 60px;
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
    width: 36px;
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
