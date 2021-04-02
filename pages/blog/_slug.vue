<template>
    <div>
        <nuxt-content :document="article" id="text" />
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const article = await $content('blog', params.slug).fetch();
        // const article = await $content (`blog/${params.slug}` || "blog").fetch();

        return { article }
    }
}
</script>

<style>
    
</style>