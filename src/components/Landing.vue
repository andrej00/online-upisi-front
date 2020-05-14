<template>
  <div id="landing">
    <div class="naslovna_slika">
      <div class="container">
        <div class="row" style="padding: 100px 0 20px 0">
          <div class="col-md-2">
            <img class="img-responsive" src="~@/assets/sum.png" alt="sum"
              style="height: 70px; width: 150px"/>
          </div>
          <div class="col-md-2" style="margin-left: 40px">
            <img class="img-responsive2" src="~@/assets/logofpmoz.png" alt="fpmoz"
              style="height: 80px; width: 160px"/>
          </div>
        </div>

        <div class="row">
          <div class="col-md" style="padding-top: 20px;">
            <h1><b>Odaberi znanje!</b></h1>
            <a class="btn btn-lg" role="button" style="color: white;" href="#">Nastavi</a>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "Landing",
};
</script>

<style lang="scss">
.naslovna_slika {
  background-image: url("~@/assets/naslovna.png");
  background-size: cover;
  background-position: center center;
  height: 600px;
  position: relative;
}
.container{
  font-family: "Open Sans", sans-serif;
}
.btn {
  background-color: #1a4283fd !important;
}

h1{
  color: #1a4283fd;
}
@media screen and (max-width: 990px) {
  .img-responsive2{
    margin-left: 45px;
  }
}
@media screen and (max-width: 768px) {
  .col-md-2{
    display: none;
  }
  .col-md{
    margin-top: 90px;
    text-align: center;
    border-radius: 10px;
    background-color: #ffffff73;
    padding-bottom: 30px;
  }
  .naslovna_slika {
  background-image: url("~@/assets/naslovna.png");
  background-position: center center;
  background-repeat: no-repeat;
  background-position: right 25% bottom 25%;
}
}
</style>
