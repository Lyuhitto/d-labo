<template>
  <div class="main-container">
    <p class="center project-name">DIYオーダーメイドスクール</p>
    <div class="project-container">
      <p class="project-section">店舗イメージ</p>
        <img class="project-image" src="/public/project-image/shop-image-01.jpg" alt="">
        <div class="project-descriptions">
          <p class="project-description">DIYリノベーション</p>
          <p class="project-description break">オーダーメイドスクール参加者募集！</p>

          <p class="project-description break">釧路市への移住検討者向けのお試し住居をDIYでリノベーションしよう！</p>

          <p class="project-description">k-Gateは釧路市中心部にあるビルの2階部分を利用し、オープン準備中の宿泊施設です。</p>
          <p class="project-description break">また、一階のk-Hackの韓国人研修生のための寮としても活用予定です。</p>

          <p class="project-description">今回はキッチンカウンター、個室を作るための間仕切り、天井の張り替え、そして壁一面の本棚作成を予定！</p>
          <p class="project-description">トライしてみたいリノベーションチームに、ぜひご参加ください。</p>
        </div>
    </div>
    <div class="container">

      <div class="details-column">

        <p class="project-section">プロジェクトの詳細</p>
        <p class="project-description">■スクール内容

講師が作業を教えながら作業を行うので安心してご参加ください！

・ペイント
・残置物撤去
・天井張り
・壁づくり
・本棚づくり

（スケジュール例）
1日目　DIYの基礎講座
2日目　現地ワークショップ　残置物撤去・塗装
3日目　現地ワークショップ　本棚、間仕切りづくり
4日目　現地ワークショップ　天井張り、片付け
※工事の進捗状況により変更有


■募集人数

15人

参加費：5000円/名　ランチ、ドリンク込み


■申し込み
フォームからお申し込みください！</p>
      </div>
      <div class="application-column">
        <div class="application-form">
          <p class="application-section">DIYで作りたいもの</p>
          <input type="text" class="text-box"/>
          <p class="application-section">備考</p>
          <textarea class="text-area"></textarea>
          <button>申し込み</button>
        </div>
      </div>
    </div>
    <div class="relational-project">
      <p class="project-section">関連プロジェクト</p>
      <div class="projects">
        <img v-for="item in relationProject" :key="item.id" :src="'/public/project-image/' + item" class="project-item" alt="">
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        relationProject: []
      }
    },
    created: function() {
      let i;
      for (i = 2; i <= 8; i++) {
        this.relationProject.push("shop-image-" + ('0' + i).slice(-2) + ".jpg")
      }
    }
  }
</script>

<style scoped>
  .main-container {
    display: flex;
    width: 100%;
    justify-content: center;
    flex-direction: column;
    align-items: center;
  }
  .project-container {
    width: 65%;
  }
  .container{
    width: 65%;
    display: flex;
    justify-content:center;
  }
  .project-name {
    font-size: 32pt;
    margin-top: 10px;
  }
  .project-section {
    font-size: 24pt;
    margin-bottom: 5px;
  }
  .details-column {
    width: 100%;
    margin-bottom: 10px;
    margin-right: 20px;
  }
  .project-image {
    width: 400px;
    height: 300px;
    background: #CCC;
    border-radius: 10px;
  }
  .project-descriptions {
    margin-top: 10px;
  }
  .project-description {
    font-size: 16pt;
    margin-bottom: 3px;
  }
  .break {
    margin-bottom: 20px;
  }
  .application-column {
    display: flex;
    flex-direction: column-reverse;
    width: 45%;
  }
  .application-form {
    width: 100%;
  }
  .application-section {
    font-size: 16px;
    margin-bottom: 5px;
  }
  .text-box {
    width: 100%;
    height: 30px;
    border: solid 2px;
    border-radius: 5px;
  }
  .text-area {
    width: 100%;
    height: 200px;
    border: solid 2px;
    border-radius: 5px;
  }
  .relational-project {
    width: 65%;
    display: inline-block;
  }
  .projects {
    display: flex;
    flex-direction: row;
    overflow-x: scroll;
  }
  .project-item {
    width: 200px;
    height: 100px;
    margin-right: 10px;
    border-radius: 5px;
  }
  .center {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>