<template>
  <div>
    <div class="naslovna_slika">
      <b-container>
        <b-row>
          <b-col>
            <div class="naslov">
              <h2><b>Online upisi</b></h2>
              <h3>U AKADEMSKU GODINU</h3>
              <h1><b>2020./2021.</b></h1>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  name: "Landing"
};
</script>

<style lang="scss">
.naslovna_slika {
  background-image: url("~@/assets/naslovna.png");
  background-size: cover;
  background-position: center center;
  height: 500px;
}
.naslov{
  color: #1a4283;
  margin-top: 70px;
}

@media screen and (max-width: 768px){
  h1{
    font-size: 2.0rem;
  }
  h2{
    font-size: 1.5rem;
  }
  h3{
    font-size: 1.25rem;
  }
}
</style>>