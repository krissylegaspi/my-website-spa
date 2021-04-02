<template>
<div>
    <div class="blogintro">
    I am grateful for all that I have learned and for all that I will learn. Welcome to this space where I can document my journey and share stories of victories, struggles, and everything in between!
    </div>
    <div class="blogs">
        <div class="articles">
            <div class="article" v-for="article of articles" :key="article.slug">
                <nuxt-link :to="{ name: 'slug', params: { slug: article.slug } }">
                <!-- <nuxt-link :to="article.path"> -->
                    <div class="article-inner">
                        <img :src="require(`~/assets/resources/${article.img}`)" alt="" />
                        <div class="detail">
                            <h3>{{ article.title }}</h3>
                            <h4>{{ article.date }}</h4>
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
        const articles = await $content("blog")
            .only(['title', 'date', 'description', 'img', 'slug'])
            .sortBy('createdAt', 'desc')
            // .sortBy('date', 'desc')
            .fetch()

        return {
            articles
        }
    }
}
</script>

<style>

.blogintro {
    display: block;
    flex-wrap: wrap;
    justify-content: space-around;
    max-width: 630px;
    margin-top: 20px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 15px;
    padding-bottom: 40px;
    font-size: 21px;
    font-family: 'Bebas Neue', cursive;
    
}

.articles {
    margin: 0 auto;
    max-width: 800px;
}

.article {
    margin-bottom: 30px;
}

a {
    text-decoration: none;
}

.article-inner {
    padding: 15px;
    background: white;
    box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    display: flex;
}

.article-inner img {
    display: block;
    width: 100%;
    max-width: 150px;
    max-height: 150px;
    object-position: center;
    object-fit: cover;
}

.article-inner .detail {
    text-decoration: none;
    padding-left: 15px;
    padding-right: 15px;
}

.article-inner .detail:hover {
    opacity: 60%;
}

h3 {
    display: inline;
    color: black;
    font-size: 24px;
    font-family: 'Homemade Apple', cursive;
    word-spacing: 0.32em;
    padding-left: 8px;
}

h4 {
    display: inline;
    color: black;
    opacity: 70%;
    text-decoration: none;
    float: right;
    padding-top: 10px;
}

p {
    color: black;
    font-size: 18px;
    text-decoration: none;
}

</style>