<script setup lang="ts">
definePageMeta({
  title: 'pages.title.top', // set resource key
})
</script>

<template>
  <div>
    <p>{{ $t('welcome') }}</p>
    <el-table mb-1 :data="[]" />
    <el-pagination :total="100" />
  </div>
</template>
