<template>
  <div>
    <Header />
    <main>
      <h1 class="page-title">
        {{ group.name }}
      </h1>
      <div class="container">
        <img :src="`/img/${group.id}.png`" alt="" />
        <p>
          {{ group.description }}
        </p>
      </div>
    </main>
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
