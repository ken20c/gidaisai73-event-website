<template>
  <div>
    <Header />
    <div>
      <main class="container-lg">
        <Carousel class="my-2" />
        <div>
          <h2 class="top-heading">企画紹介</h2>
          <div class="row row-cols-sm-1 row-cols-md-2 row-cols-lg-3 g-3">
            <div v-for="group in groups" :key="group.name">
              <!--カード全体のdiv-->
              <div class="col">
                <NuxtLink :to="`/groups/${group.id}`" class="card-link">
                  <!--カード本体のdiv-->
                  <div class="card shadow-sm">
                    <div class="row card-body p-0 m-0">
                      <div class="col-4 p-0 thumbnail-wrapper">
                        <img
                          :src="`/img/groups/${group.id}.png`"
                          :alt="`${group.name}のサムネイル`"
                          class="group-thumbnail img-fluid"
                        />
                      </div>
                      <div class="col-8 my-2 text-dark">
                        <div class="card-title lead">
                          {{ group.name }}
                        </div>
                        <small>
                          <div
                            v-show="'stage' in group"
                            class="contents-title stage"
                          >
                            {{ "stage" in group ? group.stage.title : "" }}
                          </div>
                          <div
                            v-show="'exhibition' in group"
                            class="contents-title exhibition"
                          >
                            {{
                              "exhibition" in group
                                ? group.exhibition.title
                                : ""
                            }}
                          </div>
                          <div
                            v-show="'interaction' in group"
                            class="contents-title interaction"
                          >
                            {{
                              "interaction" in group
                                ? group.interaction.title
                                : ""
                            }}
                          </div>
                          <div
                            v-show="'store' in group"
                            class="contents-title store"
                          >
                            {{ "store" in group ? group.store.title : "" }}
                          </div>
                        </small>
                      </div>
                    </div>
                  </div>
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
        <Ad />
      </main>
      <Footer />
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
.thumbnail-wrapper {
  align-items: center;
  display: flex;
}
.contents-title {
  margin: 0.2rem;
  padding: 0 0.2rem;
  border-radius: 0.3rem; /*丸みを持たせる*/
}
.badge1 {
  margin: 0;
  padding: 0 0.2rem;
  color: white;
  font-size: 0.8rem;
  border-radius: 0.3rem; /*丸みを持たせる*/
}
.contents-title.stage {
  background: #f0ceff;
}
.contents-title.exhibition {
  background: #cee3ff;
}
.contents-title.interaction {
  background: #cefff7;
}
.contents-title.store {
  background: #fffab4;
}
</style>
