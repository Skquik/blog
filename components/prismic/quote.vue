<template>
  <section class="text-gray-500 text-center">
      <q class="text-3xl text-gray-500">{{slice.primary.quote[0].text}}</q><br>
      <p>| {{slice.primary.name_of_the_author[0].text}}</p>
  </section>
</template>

<script>
export default {
    props:{
        slice:{
            Required:true, 
            Type:Object
        }
    }

}
</script>

<style>

</style>