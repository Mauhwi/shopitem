<template>
    <div class="container item-info">
      <div class="row info-box">
        <div class="col-sm-5">
          <img :src="items.imgsource" class="img-fluid" alt="Сейф Aiko TT-28" />
        </div>
        <div class="col-sm-7">
          <span class="promo">Акция</span>
          <h4>{{items.name}}</h4>
          <p>{{items.description}}</p>
          <div class="row">
            <div class="container">
              <div class="row item-main-stats">
                <div class="col-lg-6">
                  <p>Масса</p>
                  <hr />
                  <p>{{items.mass}}</p>
                </div>
                <div class="col-lg-6">
                  <p>Габариты</p>
                  <hr />
                  <p>{{items.size}}</p>
                </div>
                <div class="w-100"></div>
                <div class="col-lg-6">
                  <p>Производство</p>
                  <hr />
                  <p>{{items.production}}</p>
                </div>
                <div class="col-lg-6">
                  <p>Объём</p>
                  <hr />
                  <p>{{items.capacity}}</p>
                </div>
              </div>
            </div>
            <div class="container">
              <div class="row price-info">
                <div>
                  <h4>{{items.promoPrice}}</h4>
                  <p>{{items.price}}</p>
                </div>
                <button class="details-btn">Подробнее</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "Item",
  props: ["items"]
};
</script>
