<template>
    <div class="container-fluid">
        <section id="page-header" class="blog-header">
            <h2>/readmore</h2>
            <p> Read all case studies about our products!</p>
        </section>
        <section id="blog">
            <div v-if="user" class="toggle-edit">
                <span>Toggle Editing Post</span>
                <input type="checkbox" v-model="editPost" />
            </div>
           <div class="pro-container">
            <BlogCard
            :post="post"
            v-for="(post, index) in blogPosts.slice(0,5)"
            :key="index"
            />
           </div>
        </section>
        <section id="pagination" class="section-p1">
            <router-view class="pro">
             <router-link to="/blog/readmore">Load More</router-link>
            </router-view>
        </section>
    </div>
</template>
<script>
import BlogCard from "../components/blogs/BlogCard.vue";
export default {
  name: 'BlogView',
  components: {
    BlogCard
},
computed: {
    blogPosts() {
       return this.$store.state.blogPosts;
    },
    editPost: {
     get() {
        return this.$store.state.editPost;
     },
     set(payload) {
       this.$store.commit("toggleEditPost", payload);
     }
    },
    profileAdmin() {
     return this.$store.state.profileAdmin;
 }
},
created() {
    this.$store.dispatch('getPost');
  },
beforeUnmount () {
    this.$store.commit("toggleEditPost", false);
},
}
</script>
<style scoped>

    #blog {
        position: relative;
        margin-top: -250px;
    }
    .toggle-edit {
            display:flex;
            align-items: center;
            position: absolute;
            top: 50px;
            right:0;
    }
    span {
            margin-right: 16px;
        }
     input[type="checkbox"] {
        position: relative;
        border: none;
        /* -webkit-appearance: none; */
        outline: none;
        width: 80px;
        height: 30px;
        border-radius: 20px;
        background: #fff;
        box-shadow: 0 4px 6px -1px rgba(0,0,0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.05);
    }
    input[type="checkbox"]:before {
        content: "";
        position: absolute;
        width: 30px;
        height: 30px;
        border-radius: 20px;
        top: 0;
        left: 0;
        background: #303030;
        transform: scale(1,1);
        transition: 750ms ease all;
        box-shadow: 0 4px 6px -1px rgba(0,0,0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.05);
    }
    input:checked[type="checkbox"]:before {
        left: 52px;
        background: #fff;
    }
</style>
