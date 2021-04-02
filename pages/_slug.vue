<template>
    <div>
        <div class="back">
            <a href="javascript:history.back()">
            <!-- <a @click="goBack"> -->
                <fa :icon="['fas', 'angle-double-left']" id="icons" />
            </a>
        </div>
        <article>
            <h5>{{ article.title }}</h5>
            <h6>{{ article.date }}</h6>
            <nuxt-content :document="article" id="text" />
        </article>
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const article = await $content('blog', params.slug).fetch();
        // const article = await $content(params.slug || "blog").fetch();

        return { article }
    },
    methods: {
        goBack() {
            this.$router.push('/blog');
        }
    }
}
</script>

<style>

.back {
    max-width: 720px;
    padding-top: 30px;
    padding-bottom: 10px;
    margin: auto;
}

#icons {
    font-size: 28px;
    /* padding-left: 10px; */
    padding-bottom: 15px;
    color: rgb(255, 113, 137);
}

#icons:hover {
    color: pink;
    opacity: 80%;
}

article {
    display: block;
    margin: 0 auto;
    padding: 30px 30px;
    max-width: 720px;
}

h5 {
    font-family: 'Homemade Apple', cursive;
    margin: auto;
    content: '';
    box-sizing: border-box;
    font-size: 30px;
    word-spacing: 0.32em;
}

h6 {
    border-bottom: 1px pink solid;
    margin: auto;
    opacity: 1;
    font-family: 'Roboto Mono', monospace;
    opacity: 70%;
    padding-top: 10px;
    padding-bottom: 10px;
    width: 100%;
    font-size: 18px;
}

#text {
    padding-top: 5px;
}

</style>