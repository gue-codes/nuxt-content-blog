<template>
  <div>
    <the-header></the-header>
    <Nuxt class="mx-auto px-8 max-w-6xl" />
    <the-footer></the-footer>
  </div>
</template>

<script>
export default {}
</script>

<style>
body {
  @apply text-gray-700;
}
h1 {
  @apply text-5xl font-extralight text-gray-900 sm:text-6xl mt-6 mb-1;
}
h2 {
  @apply text-4xl font-extrabold text-green-800 mt-6 mb-1;
}
h3 {
  @apply text-2xl font-bold text-green-800 mt-6 mb-1;
}
h4 {
  @apply text-xl font-bold text-green-800 mt-6 mb-1;
}
p {
  @apply text-lg mb-4;
}
button {
  @apply bg-green-800 text-white hover:bg-green-600 font-bold rounded px-4 py-2;
}
blockquote {
  @apply bg-gray-100 border-l-4 border-gray-300 px-4 pt-4;
  padding-bottom: 0.15rem;
}
</style>
