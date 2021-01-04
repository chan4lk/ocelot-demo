<template>
  <nuxt-link :to="'/posts/' + 1" class="post-preview">
    <article>
      <div
        class="post-thumbnail"
        style="
          background-image: url('https://s27389.pcdn.co/wp-content/uploads/2019/10/retail-innovation-changing-tech-consumer-employee-demands-1024x440.jpeg');
        "
      ></div>
      <div class="post-content">
        <h1>Post title 1</h1>
        <p>Preview Text 1</p>
      </div>
    </article>
  </nuxt-link>
</template>
<script>
export default {};
</script>
<style scoped>
.post-preview {
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #ccc;
  background-color: white;
  width: 90%;
}
a {
  text-decoration: none;
  color: black;
}

@media (min-width: 850px) {
  .post-preview {
    width: 400px;
    margin: 10px;
  }
}

.post-thumbnail {
  width: 100%;
  height: 200px;
  background-position: center;
  background-size: cover;
}
.post-content {
  padding: 10px;
  text-align: center;
}

a:hover .post-content,
a:active .post-content {
  background-color: #ccc;
}
</style>
