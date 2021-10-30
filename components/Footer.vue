<template>
  <div>
    <div class="push"></div>
    <footer>
      <div class="container">
        <p></p>
        <h3 class="text-lead">第73回 岐阜大学祭</h3>
        <div>
          <p><NuxtLink :to="`/`">有志企画</NuxtLink></p>
          <p>委員会企画</p>
          <p><NuxtLink :to="`/official/owarai`">・お笑いライブ</NuxtLink></p>
          <p>
            <NuxtLink :to="`/official/gidaicollection`"
              >・岐大コレクション</NuxtLink
            >
            <!-- ・<NuxtLink :to="`/official/bingo`">ビンゴ大会</NuxtLink><br /> -->
          </p>
          <p><NuxtLink :to="`/official/vr`">・バーチャル岐阜大学</NuxtLink></p>
          <!-- ・つかさ祭<br /> -->
          <p>同時開催</p>
          <p>
            <a
              href="https://www.gifu-u.ac.jp/news/event/2021/10/entry06-11065.html"
              >・岐阜大学フェア</a
            >
          </p>
          <p><NuxtLink :to="`/contact`">お問い合わせ</NuxtLink></p>
        </div>
        <div class="logo-wrapper">
          <img src="/title.svg" class="logo" alt="" />
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.push {
  min-height: calc(100vh - 33rem);
  /* padding-bottom: 80px; */
}
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
  height: 4rem;
  margin: 1rem 0;
}
a {
  color: white;
}
a:hover {
  text-decoration: underline;
}
</style>
