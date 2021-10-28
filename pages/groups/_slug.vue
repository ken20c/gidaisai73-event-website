<template>
  <div>
    <Header />
    <main>
      <div class="container">
        <h1 class="page-title container">
          {{ group.name }}
        </h1>
        <div>
          <img :src="`/img/groups/${group.id}.png`" alt="" class="main-img" />
        </div>
        <p>
          {{ group.description }}
        </p>
        <!-- SNSリンクのdiv -->
        <div>
          <h2 v-show="group.sns.length > 0" class="top-heading">SNSリンク</h2>
          <div v-for="sns in group.sns" :key="sns.url">
            <a :href="sns.url" class="button btn-primary">
              {{ sns.service }}
            </a>
            <hr />
          </div>
        </div>
        <!-- 各企画のdiv -->
        <div class="exhibition">
          <h2 class="top-heading">展示</h2>
          <h3>
            <strong> {{ group.exhibition.title }}</strong>
          </h3>
          <p>
            {{ group.exhibition.description }}
          </p>
          <a :href="group.exhibition.contents.url" class="button btn-primary">
            <!-- なぜかうまくいかない！！
            {{ group.exhibition.contents.service }}
            -->
            リンクはこちら
          </a>
        </div>
        <div v-show="group.interaction != undefined" class="interaction">
          <h2 class="top-heading">参加型</h2>
          <h3>
            <strong> {{ group.interaction.title }}</strong>
          </h3>
          <p>
            {{ group.interaction.description }}
          </p>
          <a :href="group.interaction.contents.url" class="button btn-primary">
            リンクはこちら
          </a>
        </div>
      </div>
    </main>
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    // params.slug にはURLの末尾が入る。/groups/group1というURLはgroup1が帰ってくる。
    // params.slugがgroup1なら/content/groups配下のgroup1という名前のファイルを取得する
    // fetch() は何？
    const group = await $content(`groups/${params.slug}`).fetch();
    return { group };
  },
};
</script>

<style scoped>
.main-img {
  max-height: 15rem;
}
</style>
