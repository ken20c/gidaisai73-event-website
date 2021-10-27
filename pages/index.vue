<template>
  <div>
    <Header />
    <div>
      <h1></h1>
      <main class="container">
        <Carousel />
        <div>
          <h2 class="top-heading">企画紹介</h2>
          <div class="container">
            <div
              class="
                row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5
                g-3
              "
            >
              <div v-for="group in groups" :key="group.name">
                <div class="col">
                  <NuxtLink :to="`/groups/${group.id}`" class="card-link">
                    <div class="card shadow-sm">
                      <img
                        :src="`/img/${group.id}.png`"
                        :alt="`${group.name}のサムネイル`"
                        class="group-thumbnail"
                      />
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
