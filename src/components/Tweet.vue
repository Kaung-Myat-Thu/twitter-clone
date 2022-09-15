<template>
  <article class="border-b border-gray-600">
    <router-link to="#" class="flex p-4">
      <figure class="w-16 mr-3">
        <img
          :src="tweet.author.profile_img_url"
          :alt="tweet.author.username"
          class="w-full h-16 rounded-full object-cover"
        />
      </figure>
      <section class="flex-1">
        <div class="flex items-center">
          <span class="font-bold text-white">{{
            tweet.author.display_name
          }}</span>
          <span class="text-gray-500 font-normal ml-2">{{
            tweet.author.username
          }}</span>
        </div>

        <div :class="tweet.image ? 'mb-3' : ''">
          <p class="text-white mt-1" v-html="tweet.body"></p>
        </div>

        <figure
          v-if="tweet.image"
          class="rounded-xl border border-gray-600 overflow-hidden"
        >
          <img
            :src="tweet.image.url"
            :alt="tweet.image.alt"
            class="w-full h-44 object-cover"
          />
        </figure>

        <div class="flex items-center justify-between mt-2">
          <div class="text-gray-500">
            <i
              class="fas fa-comment p-2 mr-1 rounded-full hover:bg-emerald-900 hover:text-emerald-500"
            ></i>
            <span>{{ tweet.stats.comments.length }}</span>
          </div>
          <div class="text-gray-500">
            <i
              class="fas fa-heart p-2 mr-1 rounded-full hover:bg-emerald-900 hover:text-emerald-500"
            ></i>
            <span>{{ tweet.stats.likes.length }}</span>
          </div>
          <div class="text-gray-500">
            <i
              class="fas fa-retweet p-2 mr-1 rounded-full hover:bg-emerald-900 hover:text-emerald-500"
            ></i>
            <span>{{ tweet.stats.retweets.length }}</span>
          </div>
          <div class="text-gray-500">
            <i
              class="fas fa-share p-2 mr-1 rounded-full hover:bg-emerald-900 hover:text-emerald-500"
            ></i>
          </div>
        </div>
      </section>
    </router-link>
  </article>
</template>

<script>
export default {
  props: {
    tweet: Object,
  },
};
</script>
