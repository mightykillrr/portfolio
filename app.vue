<template>
  <NuxtLayout name="default">
    <NuxtPage v-slot="{ Component }">
      <component :is="Component"/>
    </NuxtPage>
  </NuxtLayout>
  <Teleport to="body">
    <TheNavbar/>
    <CookiesNotification/>
  </Teleport>
</template>

<script lang="ts" setup>
import {useHead} from "#head";

const images = import.meta.glob("./assets/pageMeta/*.{png,svg,ico}", {as: 'url', eager: true});


useHead({
  title: "Aniket Kotal - Full Stack Web Developer",
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: images["./assets/pageMeta/favicon-32x32.png"],
      sizes: "32x32",
    },
    {
      rel: "icon",
      type: "image/png",
      href: images["./assets/pageMeta/favicon-16x16.png"],
      sizes: "16x16",
    },
    {
      rel: "apple-touch-icon",
      type: "image/png",
      href: images["./assets/pageMeta/apple-touch-icon.png"],
      sizes: "180x180",
    },
    {
      rel: "mask-icon",
      href: images["./assets/pageMeta/safari-pinned-tab.svg"],
      color: "#5bbad5"
    },
    {
      property: "og:title",
      content: "Aniket Kotal - Full Stack Web Developer"
    },
    {
      property: "twitter:title",
      content: "Aniket Kotal - Full Stack Web Developer"
    },
    {
      name: "description",
      content: "Web Developer designing Beautiful, Intuitive Websites"
    },
    {
      name: "og:description",
      content: "Web Developer designing Beautiful, Intuitive Websites"
    },
    {
      name: "twitter:description",
      content: "Web Developer designing Beautiful, Intuitive Websites"
    },
  ],
})
</script>

