<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="channel-data">
    <div class="message">
      <ChannelMessage author="MecBOT" date="21/0/2012" isBot>
        Olá Pessoal! Proibido mandar mensagens duplicadas
      </ChannelMessage>
      <ChannelMessage
        v-for="message in 10"
        :key="message.id"
        author="Ediberto Olieira"
        date="21/0/2012"
      >
        Alguem pode me ajudar?
      </ChannelMessage>
      <ChannelMessage author="MecBOT" date="21/0/2012" isBot hasMention>
        <Mention>Ediberto Oliveira</Mention>
        Esta mensagem é duplicada, esta sujeito a punição do ADMIN!
      </ChannelMessage>
    </div>

    <div class="input-wrapper">
      <q-btn-group square push>
        <q-btn push color="grey-7" outline icon="window" />
        <q-btn push color="grey-7" outline icon="view_list" />
      </q-btn-group>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import ChannelMessage from './Channel-Message.vue';

export default defineComponent({
  name: 'MainContent',
  components: { ChannelMessage },
  setup() {
    return {};
  },
});
</script>
<style lang="scss" scoped>
.channel-data {
  grid-area: CD;
  display: flex;
  flex-direction: column;
  flex: 1;
  justify-content: space-between;
  background: var(--primary);
}

.message {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 46px - 68px);
  max-height: calc(100vh - 46px - 68px);
  overflow-y: scroll;

  .channel-message:first-child {
    margin-top: 0;
  }

  &::-webkit-scrollbar {
    width: 8px;
  }
  &::-webkit-scrollbar-thumb {
    background: var(--tertiary);
    border-radius: 4px;
  }

  &::-webkit-scrollbar-track {
    background: var(--secondary);
  }
}

.input-wrapper {
  width: 100%;
  height: 52px;
  padding: 5px 16px;
  display: flex;

  input {
    width: 100%;
    height: 44px;
    padding: 0 10px 0 57px;
    border-radius: 5px;
    background: var(--white);
    background: var(--chat-input);
    position: relative;

    &::placeholder {
      color: var(--grey);
    }
  }
}
.icon {
  color: var(--grey);
  position: relative;
  top: -50%;
  left: 14px;
  transition: 0.2s;
  width: 24px;
}
</style>
