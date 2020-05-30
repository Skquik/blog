<template>
  <section>
      <div v-for="(item, index) in slice.items" :key="index" class="py-6">
        <h2 class="text-2xl mb-2 font-bold"> {{item.title[0].text}}</h2>
        <p v-for="(par, subindex) in item.content" :key="subindex" class="mt-1">
          {{par.text}}
        </p>
      </div>
</section>
</template>

<script>
export default {
  props:{
    slice:{
      Required:true, 
    }
  }
}
</script>

<style>

</style>