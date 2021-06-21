<template>
  <div class="home">
    <Blogpost :post="WelcomeScreen" />
    <Blogpost :post="post" v-for="(post, index) in samplePosts" :key="index" />
    <div class="blog-card-wrap">
      <div class="container">
        <h3>View more Populair Blogs</h3>
        <div class="blog-cards">
          <BlogCard  :post="post" v-for="(post, index) in sampleBlogCards" :key="index" />
        </div>
      </div>
    </div>
    <div class="updates">
      <div class="container">
        <h2>never miss a post. Register for your free account today!</h2>
        <router-link class="router-button" to="#">
          Register for FireBlogs <Arrow class="arrow arrow-light"/>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
import Blogpost from "@/components/BlogPost/BlogPost";
import BlogCard from "@/components/BlogCard/BlogCard";
import Arrow from "../assets/Icons/arrow-right-light.svg";

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
      ],
    }
  },
  computed:{
    sampleBlogCards(){
      return this.$store.state.sampleBlogCards
    }
  },
  components: {
    BlogCard,
    Blogpost,
    Arrow
  },
};
</script>

<style lang="scss" scoped>
.blog-card-wrap {
  h3 {
    font-weight: 300;
    font-size: 28px;
    margin-bottom: 32px;
  }
}

.updates {
  .container {
    padding: 100px 25px;
    display: flex;
    flex-direction: column;
    align-items: center;
    @media (min-width: 800px) {
      padding: 125px 25px;
      flex-direction: row;
    }

    .router-button {
      display: flex;
      font-size: 14px;
      text-decoration: none;
      @media (min-width: 800px) {
        margin-left: auto;
      }
    }

    h2 {
      font-weight: 300;
      font-size: 32px;
      max-width: 425px;
      width: 100%;
      text-align: center;
      text-transform: uppercase;
      @media (min-width: 800px) {
        text-align: initial;
        font-size: 40px;
      }
    }
  }
}
</style>
