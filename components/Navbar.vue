<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <nuxt-link
            exact
            no-prefetch
            active-class="active"
            class="nav-link"
            to="/"
          >
            Home
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/about">
            About
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/users">
            Users
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/login">
            Login
          </nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style lang="scss">
.navbar {
  margin: 0 auto;
  width: 500px;
}
.collapse {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
}
.navbar-nav {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
}
.nav-item {
  margin: 5px;
}
.active {
  color: #fff !important;
  background-color: #007bff;
  border: 1px solid transparent;
  border-radius: 0.25rem;
}
</style>
