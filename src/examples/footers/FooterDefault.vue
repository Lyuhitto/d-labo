<script setup>
import logoDark from "@/assets/img/logos/hammer-solid.svg";
defineProps({
  brand: {
    type: Object,
    name: String,
    logo: String,
    route: "",
    default: () => ({
      name: "〇〇会社 dーLabo",
      logo: logoDark,
      route: "/"
    })
  },
  socials: {
    type: Array,
    icon: String,
    link: String,
    default: () => [
      {
        icon: '<i class="fab fa-facebook text-lg opacity-8"></i>',
        link: "https://www.facebook.com/CreativeTim/"
      },
      {
        icon: '<i class="fab fa-twitter text-lg opacity-8"></i>',
        link: "https://twitter.com/creativetim"
      },
      {
        icon: '<i class="fab fa-dribbble text-lg opacity-8"></i>',
        link: "https://dribbble.com/creativetim"
      },
      {
        icon: '<i class="fab fa-github text-lg opacity-8"></i>',
        link: "https://github.com/creativetimofficial"
      },
      {
        icon: '<i class="fab fa-youtube text-lg opacity-8"></i>',
        link: "https://www.youtube.com/channel/UCVyTG4sCw-rOvB9oHkzZD1w"
      }
    ]
  },
  menus: {
    type: Array,
    name: String,
    items: {
      type: Array,
      name: String,
      href: String
    },
    default: () => [
      {
        name: "d-Labo",
        items: [
          {
            name: "会社紹介",
            href: "https://www.creative-tim.com/presentation"
          },
          {
            name: "会社目標",
            href: "https://www.creative-tim.com/templates/free"
          },
          {
            name: "技術ブログ",
            href: "https://www.creative-tim.com/templates/premium"
          },
          { name: "blog", href: "https://www.creative-tim.com/blog" }
        ]
      },
      {
        name: "採用・人事",
        items: [
          { name: "採用情報", href: "https://iradesign.io/" },
          {
            name: "新卒・バイト",
            href: "https://www.creative-tim.com/bits"
          },
          {
            name: "ポテンシャル採用について",
            href: "https://www.creative-tim.com/affiliates/new"
          }
        ]
      },
      {
        name: "ヘルプ・お問い合わせ",
        items: [
          {
            name: "ヘルプデスク",
            href: "https://www.creative-tim.com/contact-us"
          },
          {
            name: "Q＆A",
            href: "https://www.creative-tim.com/knowledge-center"
          },
          {
            name: "お問い合わせ",
            href: "https://services.creative-tim.com/"
          },
          {
            name: "緊急連絡先について",
            href: "https://www.creative-tim.com/sponsorships"
          }
        ]
      },
      {
        name: "サイト情報",
        items: [
          {
            name: "プライバシー",
            href: "https://www.creative-tim.com/terms"
          },
          {
            name: "ユーザー情報取扱に関して",
            href: "https://www.creative-tim.com/privacy"
          },
          {
            name: "サイトマップ",
            href: "https://www.creative-tim.com/license"
          }
        ]
      }
    ]
  }
});
</script>
<template>
  <footer class="footer pt-5 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-md-3 mb-4 ms-auto">
          <div>
            <a :href="brand.route">
              <img :src="brand.logo" class="mb-3 footer-logo" alt="main_logo" />
            </a>
            <h6 class="font-weight-bolder mb-4">{{ brand.name }}</h6>
          </div>
          <div>
            <ul class="d-flex flex-row ms-n3 nav">
              <li
                class="nav-item"
                v-for="{ icon, link } of socials"
                :key="link"
              >
                <a
                  class="nav-link pe-1"
                  :href="link"
                  target="_blank"
                  v-html="icon"
                >
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div
          class="col-md-2 col-sm-6 col-6 mb-4"
          v-for="{ name, items } of menus"
          :key="name"
        >
          <h6 class="text-sm">{{ name }}</h6>
          <ul class="flex-column ms-n3 nav">
            <li class="nav-item" v-for="item of items" :key="item.name">
              <a class="nav-link" :href="item.href" target="_blank">
                {{ item.name }}
              </a>
            </li>
          </ul>
        </div>

        <div class="col-12">
          <div class="text-center">
            <p class="text-dark my-4 text-sm font-weight-normal">
              All rights reserved. Copyright ©
              {{ new Date().getFullYear() }}
              d-Labo by
              <a href="https://www.creative-tim.com" target="_blank"
                >〇〇会社 dーLabo</a
              >.
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
