<script lang="ts" setup>
import { ref } from 'vue'

const activeIndex = ref('1')
</script>

<template>
  <div>
    <ClientOnly>
      <ElMenu
        :default-active="activeIndex"
        mode="horizontal"
        :ellipsis="false"
      >
        <ElMenuItem index="0">
          LOGO
        </ElMenuItem>
        <ElMenuItem index="1">
          Processing Center
        </ElMenuItem>
        <ElSubMenu index="2">
          <template #title>
            Workspace
          </template>
          <ElMenuItem index="2-1">
            item one
          </ElMenuItem>
          <ElMenuItem index="2-2">
            item two
          </ElMenuItem>
          <ElMenuItem index="2-3">
            item three
          </ElMenuItem>
          <ElSubMenu index="2-4">
            <template #title>
              item four
            </template>
            <ElMenuItem index="2-4-1">
              item one
            </ElMenuItem>
            <ElMenuItem index="2-4-2">
              item two
            </ElMenuItem>
            <ElMenuItem index="2-4-3">
              item three
            </ElMenuItem>
          </ElSubMenu>
        </ElSubMenu>
      </ElMenu>
    </ClientOnly>
  </div>
</template>
