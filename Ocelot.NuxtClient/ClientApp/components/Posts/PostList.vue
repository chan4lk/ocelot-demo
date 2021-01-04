<template>
  <div>
    <section class="posts-list">
      <post-preview
        id="1"
        title="Hello There"
        preview-text="This is my first post"
        :thumbnail="'https://s27389.pcdn.co/wp-content/uploads/2019/10/retail-innovation-changing-tech-consumer-employee-demands-1024x440.jpeg'"
      />
      <post-preview
        id="2"
        title="Hello There"
        preview-text="This is my second post"
        :thumbnail="'https://s27389.pcdn.co/wp-content/uploads/2019/10/retail-innovation-changing-tech-consumer-employee-demands-1024x440.jpeg'"
      />
      <post-preview
        id="3"
        title="Hello There"
        preview-text="This is my third post"
        :thumbnail="'https://s27389.pcdn.co/wp-content/uploads/2019/10/retail-innovation-changing-tech-consumer-employee-demands-1024x440.jpeg'"
      />
    </section>
  </div>
</template>

<script>
export default {};
</script>
<style scoped>
.posts-list {
  display: flex;
  padding: 20px;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
