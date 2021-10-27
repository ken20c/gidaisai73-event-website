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
                      <div class="col-4 p-0">
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
                            class="contents-title stage"
                            v-show="'stage' in group"
                          >
                            <!-- <span class="badge1 badge-stage">ステージ</span> -->
                            {{ "stage" in group ? group.stage.title : "" }}
                          </div>
                          <div
                            class="contents-title exhibition"
                            v-show="'exhibition' in group"
                          >
                            <!-- <span class="badge1 badge-exhibition"
                              >動画/作品</span
                            > -->
                            {{
                              "exhibition" in group
                                ? group.exhibition.title
                                : ""
                            }}
                          </div>
                          <div
                            class="contents-title interaction"
                            v-show="'interaction' in group"
                          >
                            <!-- <span class="badge1 badge-interaction">参加型</span> -->
                            {{
                              "interaction" in group
                                ? group.interaction.title
                                : ""
                            }}
                          </div>
                          <div
                            class="contents-title store"
                            v-show="'store' in group"
                          >
                            <!-- <span class="badge1 badge-store">物販</span> -->
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
.badge-stage {
  background: #c43bff;
}
.contents-title.exhibition {
  background: #cee3ff;
}
.badge-exhibition {
  background: #3f92ff;
}
.contents-title.interaction {
  background: #cefff7;
}
.badge-interaction {
  background: #3cffdf;
  color: black;
}
.contents-title.store {
  background: #fffab4;
}
.badge-store {
  background: #ffef0c;
  color: black;
}
</style>
