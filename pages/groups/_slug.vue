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
            <a :href="sns.url" class="button btn-original">
              {{ sns.service }}
            </a>
            <hr />
          </div>
        </div>
        <!-- 使い回しスタート stage -->
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
          <p v-if="group.stage.premiereTime != undefined">
            <span>プレミア公開時刻</span>
            10月31日（日）
            {{ group.stage.premiereTime }}
          </p>
          <button class="btn btn-original-primary disabled" disabled>
            公開までしばらくお待ちください
          </button>
          <!-- <a :href="group.stage.url" target="_blank">
            <button class="btn btn-original-primary">
              視聴する
            </button>
          </a> -->
          <p class="text-muted text-center">YouTube が開きます</p>
        </div>
        <!-- 使い回し終わり -->
        <!-- 使い回しスタート exhibition -->
        <div v-if="'exhibition' in group" class="contents-title exhibition">
          <h2 v-if="group.exhibition != undefined" class="top-heading">
            動画/作品
          </h2>
          <h3>
            {{ "exhibition" in group ? group.exhibition.title : "" }}
          </h3>
          <p>
            {{ "exhibition" in group ? group.exhibition.description : "" }}
          </p>
          <div v-if="'exhibition' in group">
            <div
              v-for="content in group.exhibition.contents"
              :key="content.url"
            >
              <div>
                <p>
                  <span>使用サービス：</span>
                  {{ content.service }}
                </p>
                <p>
                  <span v-show="content.date != ''">公開予定</span>
                  {{ content.date }}
                  {{ content.time }}
                </p>
                <a :href="content.url" target="_blank">
                  <button class="btn btn-original-primary">
                    企画を見にいく
                  </button>
                </a>
                <p class="text-muted text-center">
                  {{ content.service }}が開きます
                </p>
              </div>
            </div>
          </div>
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
          <div v-for="content in group.interaction.contents" :key="content.url">
            <div>
              <p>
                <span>使用サービス：</span>
                {{ content.service }}
              </p>
              <p>
                <span v-show="content.date != ''">公開予定</span>
                {{ content.date }}
                {{ content.time }}
              </p>
              <a :href="content.url" target="_blank">
                <button class="btn btn-original-primary">企画に参加する</button>
              </a>
              <p class="text-muted text-center">
                {{ content.service }}が開きます
              </p>
            </div>
          </div>
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
          <a :href="group.store.store" target="_blank">
            <button class="btn btn-original-primary">販売ページ</button>
          </a>
          <p class="text-muted text-center">
            物販の購入は10月31日正午までとなります
          </p>
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
