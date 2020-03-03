<template>
  <div class=" container mx-auto ">
    {{posts}}
  </div>
</template>

<script>

export default {
 head () {
    return {
      title: "Bonjour c'est Paul",
    }
  },
  async asyncData({$prismic, error}){
    try{
      // Query to get blog home content
      const homepageContent = (await $prismic.api.getSingle('home')).data

      // Query to get posts content to preview
      const blogPosts = await $prismic.api.query(
        $prismic.predicates.at("document.type", "blog-post")
      )

      // Returns data to be used in template
      return {
        homepageContent,
        posts: blogPosts.results,
      }
    } catch (e) {
      console.log(e)
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  }}
</script>

