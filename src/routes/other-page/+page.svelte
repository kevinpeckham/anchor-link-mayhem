<!--
@component
Test action of cross-page anchor links.
-->

<template lang='pug'>
.bg-primary.text-white.w-screen.h-screen.px-16.py-16
  .text-24.mb-2 The Other Page
  .italic.mb-6 Test behavior of cross-page anchor links.
  +each('[1,2,3] as target')
    div: a.inline-block.border.px-3.py-2.rounded.mb-4(href="/#section-{target}") Home Page Section - {target}
</template>