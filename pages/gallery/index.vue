<template>
<section class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
    <div class="text-center pb-12">
        <h2 class="text-base font-bold text-indigo-600">
            Portfolio
        </h2>
        <h1 class="font-bold text-3xl md:text-4xl lg:text-5xl font-heading text-gray-900">
            Select a category
        </h1>
    </div>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="gallery in galleries"  :key="gallery.slug" :gallery="gallery" class="w-full bg-white rounded-lg sahdow-lg overflow-hidden flex flex-col justify-center items-center">
            <NuxtLink :to="getUrlBySlug(gallery.slug)">
            <div>
                <img class="object-center object-cover h-auto w-full" :src="gallery.header_image" alt="photo">
            </div>
            <div class="text-center py-8 sm:py-6">
                <p class="text-xl text-gray-700 font-bold mb-2">{{ gallery.title }}</p>
                <br>
            </div>
            </NuxtLink>
        </div>
    </div>
</section>
</template>

<script>
export default {
  async asyncData({ $content, params, route, $config }) {
    const fetchDocsLabel = 'fetchAllPosts'
    const galleries = await $content('gallery')
      .without(['photos', ])
      .sortBy('order')
      .fetch()
    return { galleries }
  },
  data() {
    return {};
  },
  methods: {
      getUrlBySlug(slug) {
          return "/gallery/" + slug
      }
  }
};
</script>
