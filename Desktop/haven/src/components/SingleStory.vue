<template>
  <div>
    <p>Always put on a smile</p>
    <img :src="story.url" />
    <h3>{{story.title}}</h3>
    <p>{{story.author}}</p>
    <p>{{story.post}}</p>
    <div class="comment_sec">
      <p>Leave a comment</p>
      <textarea rows="10" cols="50"></textarea>
    </div>
    <button>Post</button>
  </div>
</template>

<script>
import {mapActions} from 'vuex'
export default {
  name: "SingleStory",
  data() {
    return {
      story: { title: "", author: "", url: "", post: "" }
    };
  },
   methods: {
    ...mapActions(["displayOne"])
 
},
created() {
    return this.displayOne(this.story);
  }
}
// export default {
//     name:"SingleStory",
//     props: ["id"],
//     data() {
//         return {
//             story: [],
//             stories: [],
//             token:''
//         };
//     },
//     components: {},
//     mounted() {
//     var id = this.$route.params.id;
//     this.token = localStorage.getItem('wattpad_token')
//     const baseURI = "http://localhost:8001/user/";
//     this.$http.get(baseURI,  {headers: {"Authorization": `Bearer ${this.token}`}}).then(response => {
//       console.log(response.data);
//       this.story = response.data;
//     });
//     this.$http.get(baseURI + "story/" + id, {headers: {"Authorization": `Bearer ${this.token}`}} ).then(response => {
//       console.log(response.data);
//       this.story = response.data;
//     });
//   }

//     }
</script>

<style scoped>
h3 {
  margin-top: 4rem;
}
.comment_sec {
  margin-top: 7rem;
}
button {
  background: black;
  padding: 0.6rem 0.6rem;
  border: none;
  color: #ffffff;
  font-size: 16px;
  border-radius: 4px;
  cursor: pointer;
  border: 1px solid black;
  transition: all 200ms ease-in;
  width: 8%;
}
</style>