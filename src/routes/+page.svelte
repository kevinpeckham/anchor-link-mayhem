<!-- Example Svelte Page / Starter Web Page-->
<script lang="ts">
	const bgColors = ["bg-red-500", "bg-purple-500", "bg-blue-500"];
</script>

<template lang="pug">
	//- body
	main.relative.grid.place-content-center.bg-primary.text-white
		a.fixed.right-16.top-16.underline.underline-offset-4(href!="/other-page") Other Page
		+each('bgColors as item, index')
			+const('sectionNumber = index + 1')
			+const('location = (index == 0) ? "Bottom ↓" : "Top ↑"')
			+const('targetSectionNumber = (index == 0) ? 3 : 1')
			section.w-screen.h-screen.grid.grid-cols-1.place-items-center(
				class!="{ item }",
				id!="section-{sectionNumber}"
			)
				.text-24 Home Page - Section { sectionNumber }
				+if('index != 1')
					a.inline-block.border.px-3.py-2.rounded.bg-black.bg-opacity-10(
						href="./#section-{targetSectionNumber}"
					) Scroll to { location }
</template>
