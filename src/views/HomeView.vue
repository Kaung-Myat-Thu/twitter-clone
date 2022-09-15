<template>
  <Tweet v-for="tweet in tweets" :key="tweet._id" :tweet="tweet" />
</template>

<script>
import Tweet from "@/components/Tweet.vue";
import { ref } from "vue";
import tweet from "@/tweet";
export default {
  setup() {
    const tweets = ref(tweet);

    return {
      tweets,
    };
  },
  components: {
    Tweet,
  },
};
</script>
