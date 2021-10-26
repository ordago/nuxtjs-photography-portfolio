<template>
  <div class="flex flex-col items-center grid-cols-3 gap-4">
    <div class="flex-grow md:flex-grow-0 px-8">
      <br />
      <lingallery :addons="{ enableLargeView: true }" class="mx-auto rounded-xl" :width="width" :height="height" :items="items" />
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, route, $config }) {
    const gallery = await $content("gallery", params.slug).fetch();
    const width = 800;
    const height = 600;

    const items = gallery.photos.map(function(x) {
      return {
        src: x.photo.url,
        thumbnail: x.photo.url,
        caption: x.photo.title,
        id: x.photo.index
      };
    });

    console.log(items);

    return {
      items,
      width,
      height,
      gallery
    };
  },
  data() {
    return {};
  }
};
</script>
