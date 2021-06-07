<template>
  <div class="home">
    <Blogpost :post="WelcomeScreen" />
    <Blogpost :post="post" v-for="(post, index) in samplePosts" :key="index" />
  </div>
</template>

<script>
import Blogpost from "@/components/BlogPost/BlogPost";

export default {
  name: "Home",
  data(){
    return{
      WelcomeScreen:{
        title: "Hello Everyone",
        blogPost: "Welcome to everyone in this Blog",
        isWelcomeScreen:true,
        photo:"coding"
      },
      samplePosts:[
        {
          title: "This is title Posting NR1",
          blogHTML:"this is blogpost 1",
          blogCoverPhoto:"beautiful-stories"
        },
        {
          title: "This is title Posting NR2",
          blogHTML:"this is blogpost 2",
          blogCoverPhoto:"designed-for-everyone"
        },
      ]
    }
  },
  components: {
    Blogpost,
  },
};
</script>
