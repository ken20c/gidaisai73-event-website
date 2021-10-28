<template>
  <nav class="navbar navbar-expand-lg navbar-dark fix-top">
    <!-- <Logo class="header-logo" /> -->
    <div class="container-fluid">
      <NuxtLink class="navbar-brand" :to="`/`">
        <img class="header-logo" src="/title.svg" alt="" />
      </NuxtLink>

      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div id="navbarNavAltMarkup" class="collapse navbar-collapse">
        <div class="navbar-nav">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
          <a class="nav-link" href="#">企画一覧</a>
          <a
            class="nav-link disabled"
            href="#"
            tabindex="-1"
            aria-disabled="true"
            >企画検索</a
          >
        </div>
      </div>
    </div>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW"
      crossorigin="anonymous"
    ></script>
  </nav>
</template>

<style scoped>
.navbar {
  background: #aa47f5;
}
.header-logo {
  height: 2rem;
  width: auto;
}
</style>
