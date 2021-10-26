<template>
  <div>
    <div>
      <h2 class="top-heading">協賛</h2>
    </div>
    <div
      id="carouselExampleFade"
      class="carousel slide carousel-fade"
      data-bs-ride="carousel"
    >
      <div class="carousel-inner">
        <div
          v-for="(ad, index) in ads"
          :key="ad.id"
          :class="{ active: index == 0 }"
          class="carousel-item"
          data-bs-interval="4000"
        >
          <a :href="ad.url" target="_blank">
            <img :src="'/ad/' + ad.id + '.png'" class="d-block w-100" alt="" />
          </a>
        </div>
      </div>
      <a
        class="carousel-control-prev"
        href="#carouselExampleFade"
        role="button"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </a>
      <a
        class="carousel-control-next"
        href="#carouselExampleFade"
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
  </div>
</template>

<script>
import original from "@/assets/ad-config.json";

export default {
  data() {
    // 配列の順序をランダムに入れ替えることで、
    // 読み込むたびに広告の表示順が変わるようにしている
    const random = [];
    while (original.length > 0) {
      const randomIndex = Math.floor(Math.random() * original.length);
      const item = original[randomIndex];
      random.push(item);
      original.splice(randomIndex, 1);
    }
    return { ads: random };
  },
};
</script>

<style scoped>
#carouselExampleFade {
  max-width: 40rem;
  margin: 0 auto;
}
</style>
