<template>
    <div class="h-full bg-gray-100">
        <div class="container mx-auto bg-white p-8">
            <back-button></back-button>
            <article>
                <h1 class="text-4xl font-bold">{{ document.title[0].text }}</h1>
                <p class="text-xl py-2">introduction </p>

                <section v-for="(slice, index) in slices" :key="'slice'+index ">
                    <div v-if="slice.slice_type === 'content' " >
                       <div v-for="(item, index) in slice.items" :key="'item'+index">
                            <prismic-rich-text class="text-3xl font-bold py-2" :field="item.title "/> 
                            <prismic-rich-text class="text-xl" :field="item.content"/> 
                       </div>
                       
                    </div>
                </section>                
            </article>
        </div>
    </div>
</template>

<script>

import backButton from "@/components/backButton"

export default {
  components:{
    backButton
  },
  name: 'post',
  head () {
    return {
      title: "bonjour"
    }
  },
  async asyncData({ $prismic, params, error }) {
    try{
      // Query to get post content
      const post = (await $prismic.api.getByUID('blog-post', params.slug)).data

      // Returns data to be used in template
      return {
        slices: post.body,
        document: post,
      }
    } catch (e) {
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  },

}
</script>

<style>

</style>