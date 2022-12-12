<template>
  <div class="container">
    <div class="hero">
      <!-- dekstop -->
      <div class="d-none d-md-block">
        <div class="row mt-3">
          <div class="col-md-2"></div>
          <div class="col-md-4">
            <div class="d-flex h-100">
              <div class="justify-content-center align-self-center konten-hero">
                <h2>
                  <strong>Delicious Food Menu,</strong> <br />
                  In your gadget
                </h2>
                <p>Order NOW!</p>
                <button class="btn btn-lg btn-success"><b-icon-arrow-right></b-icon-arrow-right>&nbsp; Order</button>
              </div>
            </div>
          </div>
          <div class="col-md-6">
            <img src="../assets/img/hero.png" width="400px" />
          </div>
        </div>
      </div>
      <!-- mobile -->
      <div class="d-md-block d-md-none">
        <div class="row mt-3 d-sm-block d-md-none">
          <div class="col-md-6 text-center">
            <img src="../assets/img/hero.png" width="60%" />
          </div>
          <div class="col-md-6 mt-3">
            <div class="d-flex h-100">
              <div class="justify-content-center align-self-center">
                <h2>
                  <strong>Delicious Food Menu,</strong> <br />
                  In your gadget
                </h2>
                <p>Order NOW!</p>
                <button class="btn btn-lg btn-success"><b-icon-arrow-right></b-icon-arrow-right>&nbsp; Order</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroItem",
};
</script>

<style></style>
