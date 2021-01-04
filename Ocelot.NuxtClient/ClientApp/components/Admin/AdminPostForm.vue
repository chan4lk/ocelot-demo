<template>
  <form @submit.prevent="onSave">
    <app-control-input v-model="editedPost.author"
      >Auther Name</app-control-input
    >
    <app-control-input v-model="editedPost.title">Title</app-control-input>
    <app-control-input v-model="editedPost.thumbnailLink"
      >Thumbnail Link</app-control-input
    >
    <app-control-input v-model="editedPost.content" control-type="textarea"
      >Content</app-control-input
    >
    <app-button type="submit">Save</app-button>
    <app-button
      type="button"
      style="margin-left: 10px"
      btn-style="cancel"
      @click="onCancel"
    >
      Cancel
    </app-button>
  </form>
</template>
<script>
export default {
  props: {
    post: {
      type: Object,
      required: false,
      default() {
        return {
          author: "",
          title: "",
          thumbnailLink: "",
          content: "",
        };
      },
    },
  },
  data() {
    return {
      editedPost: this.post,
    };
  },
  methods: {
    onSave() {
      console.log(this.editedPost);
    },
    onCancel() {
      this.$router.push("/admin");
    },
  },
};
</script>
<style scoped></style>
