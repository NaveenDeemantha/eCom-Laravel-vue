<template>
  <div class="container-products">
    <div class="content-text">
        <h1>Checkout our T-Shirts Collection</h1>
    </div>
    <div class="product-grid">
      <div class="el-wrapper" v-for="n in 4" :key="n">
        <div class="box-up">
          <img class="img" src="/images/tshirt0.jpg" alt="product-img" />
          <div class="img-info">
            <div class="info-inner">
              <span class="p-name">Wear The Wild !</span><br>
              <span class="p-company">Hoomans</span>
            </div>
            <div class="a-size">
              Available sizes : <span class="size">S , M , L , XL</span>
            </div>
          </div>
        </div>
        <div class="box-down">
          <div class="h-bg">
            <div class="h-bg-inner"></div>
          </div>
          <a class="cart" href="#">
            <span class="price">LKR 2400/-</span>
            <span class="add-to-cart">
              <span class="txt">Add to Cart</span>
            </span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>


<script>

export default {
  name: "ProductCard",
};

</script>

<style scoped>

.content-text {
  text-align: center;
  margin: 2rem 0;
  color: #fff;
  font-weight: bold;
  font-size: 3rem;
  font-family: 'roboto', sans-serif;
}

.container-products {
  padding: 0.5rem 1.5rem;
  background-color: rgba(0, 0, 0, 0.9);
}

.product-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.page-wrapper {
  height: 100%;
  display: table;
}

.page-inner {
  display: table-cell;
  vertical-align: middle;
}

.el-wrapper {
  width: 360px;
  padding: 5px;
  margin: 15px 5px;
  border-radius: 15px;
  background-color: #fff;
}

@media (max-width: 991px) {
  .el-wrapper {
    width: 345px;
  }
}
@media (max-width: 767px) {
  .el-wrapper {
    width: 290px;
    margin: 30px auto;
  }
}

.box-up {
  width: 100%;
  height: 300px;
  position: relative;
  overflow: hidden;
  text-align: center;
}

.img {
  padding: 20px 0;
  transition: all 0.8s cubic-bezier(0, 0, 0.18, 1);
}

.img-info {
  position: absolute;
  width: 100%;
  bottom: 25px;
}

.p-name {
  font-family: 'Nura', sans-serif;
  font-weight: 700;
  font-size: 18px;
  color: #ffffff;
}

.p-company {
  font-family: 'Nura', sans-serif;
  font-weight: 700;
  font-size: 14px;
  text-transform: uppercase;
  color: #b7b7b7;
}

.a-size {
  position: absolute;
  width: 100%;
  bottom: -20px;
  font-family: 'PT Sans', sans-serif;
  color: #000000;
  opacity: 0;
  font-weight: 400;
  transition: all 0.3s cubic-bezier(0, 0, 0.18, 1);
}

.a-size .size {
  color: #000000;
  font-weight: 400;
}

.box-down {
  width: 100%;
  height: 60px;
  position: relative;
  overflow: hidden;
}

.h-bg {
  width: 660px;
  height: 100%;
  background-color: #3f96cd;
  position: absolute;
  left: -659px;
  transition: all 0.8s cubic-bezier(0, 0, 0.18, 1);
}

.h-bg-inner {
  width: 50%;
  height: 100%;
  background-color: #000000;
}

.cart {
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  font-family: 'Lato', sans-serif;
  font-weight: 700;
}

.cart .price {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: all 0.6s cubic-bezier(0, 0, 0.18, 1);
}

.cart .add-to-cart {
  position: absolute;
  top: 50%;
  left: 130%;
  transform: translate(-50%, -50%);
  transition: all 0.5s cubic-bezier(0, 0, 0.18, 1);
  color: #fff;
}

.el-wrapper:hover .h-bg {
  left: 0;
}

.el-wrapper:hover .price {
  left: 20px;
  color: #ffffff;
  transform: translateY(-50%);
}

.el-wrapper:hover .add-to-cart {
  left: 50%;
}

.el-wrapper:hover .img {
  filter: blur(7px);
  opacity: 0.4;
}

.el-wrapper:hover .info-inner {
  bottom: 155px;
}

.el-wrapper:hover .a-size {
  bottom: 50px;
  opacity: 1;
}



</style>
