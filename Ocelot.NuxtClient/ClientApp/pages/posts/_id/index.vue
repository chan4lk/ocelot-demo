<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">Title of the Post</h1>
      <div class="post-details">
        <div class="post-detail">Last Updated on XXX</div>
        <div class="post-detail">Written by Name</div>
      </div>
      <p class="post-content">Content of the post</p>
    </section>
    <section class="post-feedback">
      <p>
        Let me know what you think about the post, send a mail to
        <a href="mailto:admin@chanideals.com">admin@chanideals.com</a>
      </p>
    </section>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
}

.post {
  width: 100%;
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media screen and (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }

  .post {
    width: 600px;
    margin: auto;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
