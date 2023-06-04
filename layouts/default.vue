<script setup lang="ts">
import en from 'element-plus/lib/locale/lang/en'
import de from 'element-plus/lib/locale/lang/de'
import type { Language } from 'element-plus/es/locale'

const i18n = useI18n()

const locales: Record<string, Language> = {
  en,
  de,
}

const locale = computed(
  () => (
    locales[i18n.locale.value]
  ),
)
</script>

<template>
  <el-config-provider :locale="locale">
    <el-container>
      <el-header>
        <Header />
      </el-header>
      <el-main>
        <slot />
      </el-main>
      <el-footer>
        <Footer />
      </el-footer>
    </el-container>
  </el-config-provider>
</template>
