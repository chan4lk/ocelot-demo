<template>
  <div class="header">
    <ul class="nav-items">
      <li>
        <Nuxt-Link
          to="/"
        >
          Home
        </Nuxt-Link>
      </li>
      <li>
        <Nuxt-Link
          to="/users"
        >
          Users
        </Nuxt-Link>
      </li>
    </ul>
  </div>
</template>

<style scoped>
  .header {
    width: 100%;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .nav-items {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 80%;
  }
</style>
