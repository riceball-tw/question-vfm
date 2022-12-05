<script setup lang="ts">
import { ModalsContainer } from 'vue-final-modal'
import useModal from 'vue-final-modal'
import {markRaw} from 'vue'
import PlainCssConfirmModal from './PlainCssConfirmModal.vue'

const { open, close } = useModal({
  component: markRaw(PlainCssConfirmModal),
  attrs: {
    title: 'Hello World!',
    onConfirm() {
      close()
    },
  },
  slots: {
    default: '<p>The content of the modal</p>',
  },
})
</script>

<template>
  <VButton @click="open">
    Open Modal
  </VButton>

  <ModalsContainer />
</template>

