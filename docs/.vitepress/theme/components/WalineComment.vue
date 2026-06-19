<script setup lang="ts">
import { computed } from 'vue'
import { useData } from 'vitepress'
import { Waline } from '@waline/client/component'
import '@waline/client/style'

const serverURL = 'https://api.zcservice.houlang.cloud/comment/d1f4a600b4daab96a8f24cb0ca704204'

const { isDark } = useData()
const darkMode = computed(() => isDark.value ? 'html[class~="dark"]' : false)

const emojiList = [
  'https://unpkg.com/@waline/emojis@1.2.0/bilibili/',
  'https://unpkg.com/@waline/emojis@1.2.0/qq/',
  'https://unpkg.com/@waline/emojis@1.2.0/tieba/',
]
</script>

<template>
  <div class="waline-container">
    <Waline
      :serverURL="serverURL"
      :lang="'zh-CN'"
      :dark="darkMode"
      :imageUploader="false"
      :emoji="emojiList"
      :requiredMeta="['nick', 'mail']"
      :placeholder="'欢迎留下你的评论~'"
    />
  </div>
</template>

<style scoped>
.waline-container {
  margin-top: 48px;
  padding-top: 32px;
  border-top: 1px solid var(--vp-c-divider);
  --waline-theme-color: var(--vp-c-brand-1);
  --waline-active-color: var(--vp-c-brand-2);
}
</style>
