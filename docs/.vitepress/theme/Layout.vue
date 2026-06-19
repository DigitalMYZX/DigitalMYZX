<script setup lang="ts">
import DefaultTheme from 'vitepress/theme'
import WalineComment from './components/WalineComment.vue'

const { Layout } = DefaultTheme
</script>

<template>
  <Layout>
    <template #doc-after>
      <ClientOnly>
        <WalineComment />
      </ClientOnly>
    </template>
  </Layout>
</template>
