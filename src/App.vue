<template>
  <div id="app">
    <Header />

    <p class="container">
      Идейные соображения высшего порядка, а также сложившаяся структура организации представляет
      собой интересный эксперимент проверки направлений прогрессивного развития.
    </p>
    <div id="carousel" class="carousel slide" data-ride="false">
      <div class="carousel-inner container">

        <Items v-bind:itemInfo="itemInfo"/>

        <a class="carousel-control-prev" href="#carousel" role="button" data-slide="prev">
          <span>
            <img src="/Vector.png" />
          </span>
          <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next" href="#carousel" role="button" data-slide="next">
          <span>
            <img src="/Vector.png" />
          </span>
          <span class="sr-only">Next</span>
        </a>
      </div>
      <ol class="carousel-indicators">
        <li data-target="#carousel" data-slide-to="0" class="active"></li>
        <li data-target="#carousel" data-slide-to="1"></li>
        <li data-target="#carousel" data-slide-to="2"></li>
      </ol>
    </div>
  </div>
</template>

<script>
import Items from "./components/Items";
import Header from "./components/Header";
import axios from "axios";

export default {
  name: "App",

  components: {
    Items,
    Header,
  },

  data () {
    return {
      itemInfo: [],
    }
  },

  methods: {
    fetchData() {
      axios.get("/items.json").then(response => this.itemInfo = response.data)
      .catch(error => console.log(error));
    },
  },

  created() {
    this.fetchData();
  },
};
</script>

<style>
html body {
  font-family: 'Roboto', sans-serif;
  min-width: 320px;
  padding: 0 10px;
}
html body .container {
  margin-bottom: 0;
}
html body .nav {
  align-items: baseline;
}
html body .nav .nav-link {
  color: #8F8F9D;
  text-transform: uppercase;
  font-size: 12px;
  font-weight: bold;
}
html body .nav .nav-active {
  font-size: 32px;
  color: #19191E;
  text-transform: none;
}
.item-info {
  margin: 30px;
  border: 1px solid #E1E1E6;
}
.item-info .info-box {
  position: relative;
  padding: 60px 40px;
}
.item-info .info-box .col-sm-5 {
  padding-bottom: 10px;
}
.item-info .info-box .col-sm-7 {
  position: relative;
}
.item-info .info-box .col-sm-7 .promo {
  position: absolute;
  top: -28px;
  background: #FFAA00;
  color: white;
  border-radius: 2px;
  padding: 4px 6px;
  text-transform: uppercase;
  font-size: 10px;
}
.item-info .info-box .col-sm-7 h4 {
  font-weight: bold !important;
}
.item-info .info-box .col-sm-7 .row .container {
  padding-left: 0px;
  padding-right: 0px;
}
.carousel-control-prev {
  min-width: 20px;
  width: 3% !important;
  opacity: 1 !important;
}
.carousel-control-prev span {
  background: white;
  padding: 8px;
  filter: drop-shadow(0px 4px 32px rgba(0, 0, 0, 0.1));
}
.carousel-control-next {
  min-width: 20px;
  width: 3% !important;
  opacity: 1 !important;
}
.carousel-control-next span {
  background: white;
  padding: 8px;
  filter: drop-shadow(0px 4px 32px rgba(0, 0, 0, 0.1));
}
.carousel-control-next span img {
  transform: rotate(180deg);
}
.carousel {
  min-width: 320px;
}
.carousel-indicators .active {
  background-color: #2244CC !important;
  width: 24px !important;
}
.carousel-indicators li {
  background-color: #191928 !important;
  width: 16px !important;
  height: 4px !important;
}
.item-main-stats {
  padding-bottom: 6px;
  border-bottom: solid 1px #E1E1E6;
}
.item-main-stats div {
  color: #6C6C71;
  display: flex;
  justify-content: space-between;
  font-size: 14px;
}
.item-main-stats div hr {
  border-top: none;
  border-bottom: 1px dotted #6C6C71;
  height: 1px;
  flex-grow: 3;
}
.price-info {
  padding-top: 14px;
  justify-content: space-between;
  margin-bottom: 40px;
}
.price-info div {
  display: flex;
  align-items: flex-end;
}
.price-info div h4 {
  padding-left: 15px;
}
.price-info div p {
  text-decoration-line: line-through;
  font-size: 14px;
  color: #6C6C71;
  font-weight: normal;
  margin-bottom: 6px;
  align-self: center;
}
.price-info .details-btn {
  background: #2244CC;
  color: white;
  border-radius: 4px;
  border: none;
  font-size: 12px;
  padding: 12px 24px;
  margin-left: 10px;
  text-transform: uppercase;
  align-self: flex-end;
}
</style>
