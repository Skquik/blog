<template>
    <div class="h-full ">
        <div class="container mx-auto bg-white p-8 " style="max-width:60%">
            <nuxt-link to="/blog" class="underline">retour à la liste</nuxt-link>
            <article>
                <h1 class="text-4xl font-bold">{{ document.title[0].text }}</h1>
                <p class="text-xl py-2">{{document.description[0].text}} </p>
                <section v-for="(slice, index) in slices" :key="'slice'+index ">
                  <div v-if="slice.slice_type === 'content' " >
                      <pr-content :slice="slice"/>
                  </div>
                  <div v-if="slice.slice_type === 'quote'">
                    <pr-quote :slice="slice"/>
                  </div>       
                  <div v-if="slice.slice_type === 'hero-section'">
                    <pr-hero :slice="slice"></pr-hero>
                  </div>             
                </section>                
            </article>
        </div>
    </div>
</template>

<script>

import quote from '@/components/prismic/quote'
import content from '@/components/prismic/content'
import hero from '@/components/prismic/hero'

export default {
  components:{
    "pr-quote": quote, 
    "pr-content": content, 
    "pr-hero": hero
  },
  name: 'post',
   head () {
    if(typeof this.document !== "undefined"){
      return { title : "En cours de chargement"}
    }
    return { title: document.title[0].text}
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