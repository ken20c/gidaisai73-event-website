<template>
  <footer>
    <h3>第73回 岐阜大学祭</h3>
    <p class="paragraph">
      <NuxtLink :to="`/`">有志企画</NuxtLink><br />
      委員会企画<br />
      ・<NuxtLink :to="`/official/owarai`">お笑いライブ</NuxtLink><br />
      ・<NuxtLink :to="`/official/gidaicollection`">岐大コレクション</NuxtLink
      ><br />
      ・<NuxtLink :to="`/official/bingo`">ビンゴ大会</NuxtLink><br />
      ・<NuxtLink :to="`/official/vr`">バーチャル岐阜大学</NuxtLink><br />
      同時開催イベント<br />
      ・つかさ祭り<br />
      ・<a href="https://www.gifu-u.ac.jp/news/event/2021/10/entry06-11065.html"
        >岐阜大学フェア</a
      ><br />
      <NuxtLink :to="`/contact`">お問い合わせ</NuxtLink>
    </p>
    <div class="logo-wrapper">
      <img src="/title.svg" class="logo" alt="" />
    </div>
  </footer>
</template>

<style scoped>
footer {
  margin-top: 3rem;
  padding-top: 0.5rem;
  background: #aa47f5;
}
h3 {
  color: white;
}
p {
  margin: 1rem;
  color: white;
}
.logo-wrapper {
  text-align: center;
}
.logo {
  max-width: 50%;
  margin: 1rem 0;
}
a {
  color: white;
}
a:hover {
  text-decoration: underline;
}
</style>
