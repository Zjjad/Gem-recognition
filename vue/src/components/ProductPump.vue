<template>
  <header-bar></header-bar>
    <div class="container">
      <div class="page-header">
        <div class="container">
          <div class="row">
            <div class="col-md-12">
              <div class="content">
                <h1 class="page-name">Shop</h1>
                <nav aria-label="breadcrumb">
                  <ol class="breadcrumb">
                    <li class="breadcrumb-item"><router-link style="text-decoration: none" to="/">Home</router-link></li>
                    <li class="breadcrumb-item active" aria-current="page">Shop</li>
                  </ol>
                </nav>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="title text-center">
          <h2>Trendy Products</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-4" v-for="index in 9" :key="index">
          <div class="product-item">
            <div class="product-thumb">
              <div style="max-width: 1241px; max-height: 775px;">
                <div style="left: 0px; width: 100%; height: 0px; position: relative; padding-bottom: 62.4496%; overflow: hidden;">
                  <iframe :src="`/static/Pump_${index}.html`"
                          :id="`ssss${index}`"
                          allowfullscreen
                          style="position: absolute; top: 0px; left: 0px; height: 100%; width: 1px; min-width: 100%; *width: 100%;"
                          frameborder="0"
                          scrolling="no">
                  </iframe>
                </div>
              </div>
              <div class="product-content">
                <h4><router-link to="/PumpSingle">Pump</router-link></h4>
                <p class="price">99$</p>
              </div>
            </div>
          </div>
          <div class="product-content">
            <h4><router-link to="`#`"></router-link></h4>
            <p class="price"></p>
          </div>
        </div>
      </div>
    </div>

  <footer-bar></footer-bar>
</template>

<script>
import HeaderBar from "@/components/HeaderBar.vue";
import FooterBar from "@/components/FooterPage.vue";

export default {
  name: "ProductPump",
  components: { FooterBar, HeaderBar },
}
</script>

<style scoped>
@import "../css/_common.css";
.TopPicture {
  padding-bottom: 80px;
}
.carousel-inner {
  /* 设置内部图片的宽度和高度 */
  width: 100%;
  height: 100%;
}

.carousel-item img {
  /* 图片充满整个容器 */
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.carousel-caption {
  color: white; /* 文字颜色 */
  /* 调整文字位置，可以根据需要修改下面的属性值 */
  position: absolute;
  top: 50%; /* 从顶部位置的百分比 */
  left: 50%; /* 从左侧位置的百分比 */
  transform: translate(-50%, -50%); /* 用于将元素居中 */
}
.carousel-caption h5 {
  font-size: 36px; /* 调整标题字体大小 */
}
.carousel-caption p {
  color: white;
  font-size: 24px; /* 调整描述字体大小 */
}
.carousel-item.active .carousel-caption h5,
.carousel-item.active .carousel-caption p {
  opacity: 1; /* 当元素在 active 状态时，透明度为 1，即不透明 */
}
.carousel-caption h5{
  opacity: 0; /* 初始状态为透明 */
  transition: opacity 1.5s ease-in-out; /* 添加渐显的过渡效果 */
}
.carousel-caption p {
  opacity: 0; /* 初始状态为透明 */
  transition: opacity 2.5s ease-in-out; /* 添加渐显的过渡效果 */
}
.product{
  padding: 80px;
}
.product-item{
  margin-bottom: 30px;
}
.product-thumb{
  position: relative;
}
.product-item .product-thumb {
  position: relative;
}
.product-content h4 a {
  color: #000;
  text-decoration: none;
}
.product-content h4 {
  font-size: 16px;
  font-weight: 400;
  margin-top: 15px;
  margin-bottom: 6px;
}
.mid{
  padding: 80px 0;
}
.title {
  padding: 20px 0 30px;
}
.text-center {
  text-align: center;
}
.title h2 {
  font-size: 18px;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 2px;
}
.category-box {
  background-size: cover;
  margin-bottom: 30px;
  min-height: 250px;
  position: relative;
  overflow: hidden;
  width: 100%;
}
.category-box.category-box-2 {
  min-height: 450px;
  margin-bottom: 0px;
}
.category-box .content {
  position: absolute;
  z-index: 999;
  top: 0;
  padding: 25px;
}
.category-box .content h3 {
  margin: 0;
  color: #333;
  font-size: 20px;
  font-weight: 500;
}
.category-box .content p {
  margin: 6px 0 0;
}
.category-box img {
  transition: all 0.3s ease-in-out;
  width: 100%;
  height: auto;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.category-box:hover img {
  transform: scale(1.2); /* 鼠标悬停时放大图像 */
}
/* .call-to-action */
.call-to-action {
  padding: 80px;
  /* .subscription-form */
}

/* @include mobile */
.call-to-action .subscription-form {
  display: block;
}

/* input */
.call-to-action .subscription-form input {
  height: 50px;
}

/* @include mobile */
.call-to-action .subscription-form input {
  text-align: center;
}

/* .btn-main */
.call-to-action .subscription-form .btn-main {
  font-size: 14px;
}

/* @include mobile */
.call-to-action .subscription-form .btn-main {
  width: 100%;
}
.call-to-action .subscription-form input {
  height: 50px;
}
.form-control {
  box-shadow: none;
  border-radius: 0;
  &:focus {
    box-shadow:none;
    border:1px solid $primary-color;
  }
}
.instagram-feed {
  text-align: center;
  padding: 80px;
}
.instagram-feed a {
  margin: 6px;
  margin-right: 10px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}
.instagram-feed a:hover img {
  filter: grayscale(10);
}
.instagram-feed a img {
  width: 100%;
  max-height: 180px;
  -o-object-fit: cover;
  object-fit: cover;
}
</style>
