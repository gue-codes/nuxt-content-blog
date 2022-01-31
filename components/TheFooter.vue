<template>
  <footer class="mt-16">
    <div class="text-center text-gray-400 p-4 border-t border-gray-100">
      ©{{ theyear }} NuxtBlog
    </div>
  </footer>
</template>

<script>
export default {
  computed: {
    theyear() {
      return new Date(Date.now()).getFullYear()
    },
  },
}
</script>
