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
        <!-- stageのdiv -->
        <div v-if="'stage' in group" class="contents-title stage">
          <h2 v-if="group.stage != undefined" class="top-heading">
            ステージ企画
          </h2>
          <h3>
            {{ "stage" in group ? group.stage.title : "" }}
          </h3>
          <p>
            {{ "stage" in group ? group.stage.description : "" }}
          </p>
          <a
            v-if="group.stage.url != undefined"
            :href="group.stage.url"
            class="button btn-primary"
          >
            リンクはこちら
          </a>
        </div>
        <!-- 使い回しスタート exhibition -->
        <div v-if="'exhibition' in group" class="contents-title exhibition">
          <h2 v-if="group.exhibition != undefined" class="top-heading">展示</h2>
          <h3>
            {{ "exhibition" in group ? group.exhibition.title : "" }}
          </h3>
          <p>
            {{ "exhibition" in group ? group.exhibition.description : "" }}
          </p>
          <a
            v-if="group.exhibition.contents.url != undefined"
            :href="group.exhibition.contents.url"
            class="button btn-primary"
          >
            リンクはこちら
          </a>
        </div>
        <!-- 使い回し終わり -->
        <!-- 使い回しスタート interaction-->
        <div v-if="'interaction' in group" class="contents-title interaction">
          <h2 v-if="group.interaction != undefined" class="top-heading">
            参加型
          </h2>
          <h3>
            {{ "interaction" in group ? group.interaction.title : "" }}
          </h3>
          <p>
            {{ "interaction" in group ? group.interaction.description : "" }}
          </p>
          <a
            v-if="group.interaction.contents.url != undefined"
            :href="group.interaction.contents.url"
            class="button btn-primary"
          >
            リンクはこちら
          </a>
        </div>
        <!-- 使い回し終わり -->
        <!-- 使い回しスタート store -->
        <div v-if="'store' in group" class="contents-title store">
          <h2 v-if="group.store != undefined" class="top-heading">販売</h2>
          <h3>
            {{ "store" in group ? group.store.title : "" }}
          </h3>
          <p>
            {{ "store" in group ? group.store.description : "" }}
          </p>
          <a
            v-if="group.store.store != undefined"
            :href="group.store.store"
            class="button btn-primary"
          >
            リンクはこちら
          </a>
        </div>
        <!-- 使い回し終わり -->
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
