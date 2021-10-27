<template>
  <div>
    <Header />
    <div>
      <h1></h1>
      <main class="container">
        <Carousel />
        <div>
          <h2 class="top-heading">企画紹介</h2>
          <!--コンテナクラスを削除しカードの幅を大きくした-->
          <div class="">
            <div
              class="
                row row-cols-1 row-cols-sm-1 row-cols-md-2 row-cols-lg-3
                g-3
              "
            >
              <div v-for="group in groups" :key="group.name">
                <!--カード全体のdiv-->
                <div class="col">
                  <NuxtLink :to="`/groups/${group.id}`" class="card-link">
                    <!--カード本体のdiv-->
                    <div class="card shadow-sm">
                      <div class="row no-gutters">
                        <div class="col-4 col-sm-4 col-md-4 col-lg-5">
                          <img
                            :src="`/img/${group.id}.png`"
                            :alt="`${group.name}のサムネイル`"
                            class="group-thumbnail img-fluid"
                          />
                        </div>
                        <div class="col-8 col-sm-8 col-md-8 col-lg-7">
                          <div class="card-body text-dark">
                            <h4 class="card-title">
                              {{ group.name }}
                            </h4>
                            <p>
                              {{ group.description }}
                            </p>
                            <small class="text-muted">ID:{{ group.id }}</small>
                          </div>
                        </div>
                      </div>
                    </div>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </div>
        </div>
        <Ad />
      </main>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const groups = await $content("groups").fetch();
    return { groups };
  },
};
</script>
