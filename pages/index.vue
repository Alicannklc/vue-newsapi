<template>



<div class="container my-12 mx-auto px-4 md:px-12">
    <div class="flex flex-wrap -mx-1 lg:-mx-4">

        <!-- Column -->
        <div class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3" v-for="(article, index) in articles" :key="index">

            <!-- Article -->
            <article class="overflow-hidden rounded-lg shadow-lg">

                                        <a :href="article.url" target="_blank">
                   <img class="block h-auto w-full" :src="article.urlToImage" :alt="article.title">
                  
                </a>

                <header class="flex items-center justify-between leading-tight p-2 md:p-4">
                    <h1 class="text-lg">
                        <a class="no-underline hover:underline text-black" href="#">
                            {{ article.title }}
                        </a>
                    </h1>
                   
                </header>

                <footer class="flex items-center justify-between leading-none p-2 md:p-4">
                    <a class="flex items-center no-underline hover:underline text-black" href="#">
                        <img alt="Placeholder" class="block rounded-full" src="https://picsum.photos/32/32/?random">
                        <p class="ml-2 text-sm">
                            Author Name
                        </p>
                    </a>
                    <a class="no-underline text-grey-darker hover:text-red-dark" href="#">
                        <span class="hidden">Like</span>
                        <i class="fa fa-heart"></i>
                    </a>
                </footer>

            </article>
            <!-- END Article -->

        </div>
        <!-- END Column -->



        </div>
        <!-- END Column -->

    </div>
</div>
</template>

<script>
   import axios from 'axios'

export default {
        async asyncData({ app }) {
            const { articles } = await app.$axios.$get(
                `https://newsapi.org/v2/top-headlines?country=de&apiKey=e2c1ab9a6eb34b68b3ad92daf3284ffb`
            );

            return { articles };
        },
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

</style>
