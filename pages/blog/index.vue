<template>
  <div class="h-full ">
      <div class="container mx-auto" style="max-width:60%">
        <div class="flex justify-between items-stretch">
          <nuxt-link to='/' class="underline flex-1 self-center ">
              Accueil
          </nuxt-link>
          <h1 class="flex-auto text-center text-4xl">Liste des articles</h1>
          <div class="flex-1 "></div>
        </div>
          <p class="text-center">Une liste d'article avec ma vision</p>
          <div class="flex flex-col">
               
            <div class="bg-white shadow-lg rounded-lg  p-8 my-4 flex flex-col justify-around bg-teal-200 " v-for="(item, index) in blogPosts" :key="'item'+index">
              <nuxt-link :to="{ name: 'blog-slug', params: { slug:item.uid }}" prefetch><h2 class="font-bold text-3xl hover:underline">{{$prismic.asText(item.data.title)}} </h2></nuxt-link>
              <p class="text-xl">{{$prismic.asText(item.data.description)}}</p>
            </div>

          </div>
         
      </div>
  </div>
</template>

<script>
export default {
name:"posts", 
head(){
  return{
    title: "Liste des articles"
  }
}, 
async asyncData({ $prismic, params, error}){
  try{
    console.log("bonjour")
    const blogPosts = await $prismic.api.query(
      $prismic.predicates.at(
        "document.type", "blog-post"),
        { orderings : '[document.first_publication_date desc]' }
    )
    return{
      blogPosts: blogPosts.results
    }
  }catch(e){
    console.log(e)
}
}


}
</script>

<style>

</style>