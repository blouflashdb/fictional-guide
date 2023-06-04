<script setup lang="ts">
import en from 'element-plus/lib/locale/lang/en'
import de from 'element-plus/lib/locale/lang/de'
import type { Language } from 'element-plus/es/locale'

const route = useRoute()
const { t } = useI18n()
const head = useLocaleHead({
  addDirAttribute: true,
  identifierAttribute: 'id',
  addSeoAttributes: true,
})
const title = computed(() => t('layouts.title', { title: t(route.meta.title as string ?? 'TBD') }))

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
  <div>
    <Html :lang="head.htmlAttrs?.lang" :dir="head.htmlAttrs?.dir">
      <Head>
        <Title>{{ title }}</Title>
        <template v-for="link in head.link" :key="link.id">
          <Link :id="link.id" :rel="link.rel" :href="link.href" :hreflang="link.hreflang" />
        </template>
        <template v-for="meta in head.meta" :key="meta.id">
          <Meta :id="meta.id" :property="meta.property" :content="meta.content" />
        </template>
      </Head>
      <Body>
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
      </Body>
    </Html>
  </div>
</template>
