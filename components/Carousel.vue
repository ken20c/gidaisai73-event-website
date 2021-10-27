<template>
  <div id="main-carousel" class="carousel slide" data-bs-ride="carousel">
    <ol class="carousel-indicators">
      <li
        data-bs-target="#main-carousel"
        data-bs-slide-to="0"
        class="active"
      ></li>
      <li data-bs-target="#main-carousel" data-bs-slide-to="1"></li>
      <li data-bs-target="#main-carousel" data-bs-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="/img/carusel/owarai.png" class="d-block w-100" alt="" />
      </div>
      <div class="carousel-item">
        <img src="/img/carusel/vr.png" class="d-block w-100" alt="" />
      </div>
      <div class="carousel-item">
        <img
          src="/img/carusel/gidaicollection.png"
          class="d-block w-100"
          alt=""
        />
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#main-carousel"
      role="button"
      data-bs-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#main-carousel"
      role="button"
      data-bs-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </a>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW"
      crossorigin="anonymous"
    ></script>
  </div>
</template>

<style scoped>
#main-carousel {
  max-width: 900px;
  margin: auto;
}
</style>
