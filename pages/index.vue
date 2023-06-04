<script setup lang="ts">

</script>

<template>
  <div>
    <p>{{ $t('welcome') }}</p>
    <el-table mb-1 :data="[]" />
    <el-pagination :total="100" />
  </div>
</template>
