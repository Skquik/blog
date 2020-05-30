<template>
  <section class="bg-red-500">
    <img :src="slice.primary.hero.url" :alt="slice.primary.hero.alt"/>
  </section>
</template>

<script>
export default {
    props:{
        slice:{
            Required:true
        }
    }
}
</script>

<style>

</style>