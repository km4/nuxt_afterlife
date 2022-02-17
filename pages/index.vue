<template>
  <div>
    <img :src="url" alt="" />
  </div>
</template>

<script>
const API = 'https://dog.ceo/api/breeds/'
const getTheList = API + 'list/all'
export default {
  async asyncData({ params, $axios }) {
    const { message, status } = await $axios.$get(
      'https://dog.ceo/api/breeds/image/random'
    )

    return { url: message }
  },
}
</script>
