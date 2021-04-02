<template>
<div>
    <div class="blogintro">
    I am grateful for all that I have learned and for all that I will learn. Welcome to this space where I can document my journey and share stories of victories, struggles, and everything in between!
    </div>
    <div class="blogs">
        <div class="articles">
            <div class="article" v-for="article of articles" :key="article">
                <nuxt-link :to="{ name: 'slug', params: { slug: article.slug } }">
                    <div class="article-inner">
                        <!-- <img :src="require(`~/assets/resources/${article.img}`)" alt="" /> -->
                        <div class="detail">
                            <h3>{{ article.title }}</h3>
                            <p>{{ article.description }}</p>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const articles = await $content('blog', params.slug)
            .only(['title', 'description', 'img', 'slug'])
            .sortBy('createdAt', 'desc')
            .fetch()

        return {
            articles
        }
    }
}
</script>

<style>

.blogintro {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    max-width: 630px;
    margin-top: 20px;
    margin-left: auto;
    margin-right: auto;
    padding-bottom: 40px;
    font-size: 21px;
    font-family: 'Bebas Neue', cursive;
    
}

.articles {
    margin: 0 auto;
    max-width: 600px;
}

.article {
    margin-bottom: 15px;
}

.article-inner {
    padding: 15px;
    background: #FFF;
    box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    display: flex;
}

.article-inner img {
    display: block;
    width: 100%;
    max-width: 300px;
}

.article-inner .detail {
    padding-left: 15px;
    padding-right: 15px;
}

h3 {
    color: #212121;
    font-size: 24px;
    text-decoration: none;
    font-family: 'Homemade Apple', cursive;
}

h3:hover {
    text-decoration: underline;
}

p {
    color: #888;
    font-size: 18px;
    text-decoration: none;
}

</style>