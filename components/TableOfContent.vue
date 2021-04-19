<template>
  <nav>
    <ul>
      <h2>Table of content</h2>
      <li v-for="link of toc" :key="link.id">
        <span class="icon icon-link"></span>
        <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    toc: {
      type: Array,
      required: true,
    },
  },
}
</script>
