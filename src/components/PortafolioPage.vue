<template>
  <section class="section bg-custom-gray" id="portfolio">
    <div class="container">
      <h1 class="mb-5"><span class="text-danger">My</span> Portfolio</h1>
      <div class="portfolio">
        <div class="filters">
          <a href="#" data-filter=".new" class="active"> New </a>
          <a href="#" data-filter=".web"> Web </a>
          <a href="#" data-filter=".ia"> IA </a>
          <a href="#" data-filter=".data"> Data </a>
        </div>
        <div class="portfolio-container">
          <div
            v-for="(item, index) in projects"
            v-bind:key="index"
            class="col-md-6 col-lg-4"
            :class="[item.category, index < 10 ? 'new' : '']"
          >
            <div class="portfolio-item">
              <img :src="item.img" class="img-fluid" alt="Promolider" />
              <div class="content-holder">
                <a class="img-popup"></a>
                <div class="text-holder">
                  <h6 class="title">{{ item.name }}</h6>
                  <p class="subtitle">
                    {{ item.description }}
                    <a
                      class="social-link text-dark"
                      target="_blank"
                      :href="item.link"
                      >{{ item.link }}</a
                    >
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import PromoliderImg from "../assets/imgs/promolider.png";
import SodexoImg from "../assets/imgs/sodexo.png";
import ReyesImg from "../assets/imgs/reyes-free.png";
import VoucherImg from "../assets/imgs/voucher.png";
import SantaCruzImg from "../assets/imgs/santa-cruz1.png";
export default {
  name: "PortafolioPage",

  data() {
    return {
      projects: [
        {
          name: "Reyes del Free",
          description:
            "freestyle related forum. Personal project using Django. Available in ",
          link: "https://github.com/IngYulber/reyes_free",
          img: ReyesImg,
          category: "web",
        },
        {
          name: "Sistema de Cobranza",
          description:
            "Web system to manage the collection of the company Santa Cruz de Huachipa. Available in ",
          link: "https://github.com/IngYulber/santa-cruz",
          img: SantaCruzImg,
          category: "web",
        },
        {
          name: "Promolider",
          description:
            "Gamified educational platform with artificial intelligence and an economic benefit plan for producers, students and distributors. Vue + Laravel.",
          img: PromoliderImg,
          category: "web",
        },
        {
          name: "Sodexo Fix",
          description:
            "web system that digitizes documents using artificial intelligence. Vue + Django Rest Framework.",
          img: SodexoImg,
          category: "web",
        },
        {
          name: "Voucher Dataset",
          description: "Available in ",
          link:"https://www.kaggle.com/datasets/odejohn/voucher",
          img: VoucherImg,
          category: "data",
        },
      ],
    };
  },
};
</script>

<style>
</style>