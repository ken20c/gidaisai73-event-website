<template>
  <div>
    <Header />
    <div>
      <main class="container-lg">
        <Carousel class="my-2" />
        <div>
          <h2 class="top-heading">企画紹介</h2>
          <!--コンテナクラスを削除しカードの幅を大きくした-->
          <div class="">
            <div class="row row-cols-sm-1 row-cols-md-2 row-cols-lg-3 g-3">
              <div v-for="group in groups" :key="group.name">
                <!--カード全体のdiv-->
                <div class="col">
                  <NuxtLink :to="`/groups/${group.id}`" class="card-link">
                    <!--カード本体のdiv-->
                    <div class="card shadow-sm">
                      <div class="row card-body p-0 m-0">
                        <div class="col-4 p-0">
                          <img
                            :src="`/img/groups/${group.id}.png`"
                            :alt="`${group.name}のサムネイル`"
                            class="group-thumbnail img-fluid"
                          />
                        </div>
                        <div class="col-8">
                          <div class="text-dark">
                            <div class="card-title lead">
                              {{ group.name }}
                            </div>
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

<style scoped>
.group-thumbnail {
  width: 100%;
}
</style>
