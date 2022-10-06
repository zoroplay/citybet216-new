<template>
  <div>
    <nav class="navbar navbar-expand-sm py-3 navbar-light bg-transparent">
      <div class="tl_logo">
        <a href="/">
          <img src="~/assets/img/logo.png" style="height: 50px" alt="" />
        </a>
      </div>
      <button
        class="navbar-toggler d-lg-none"
        type="button"
        data-toggle="collapse"
        data-target="#collapsibleNavId"
        aria-controls="collapsibleNavId"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavId">
        <ul class="navbar-nav mr-4 ml-auto mt-2 mt-lg-0">
          <!-- <li class="nav-item active">
            <a
              class="tl_simple_link tl_simple_link-accent mr-2 d-flex align-items-center"
              href="#"
              >PROMOTIONS</a
            >
          </li> -->
          <li class="nav-item">
            <!-- <a class="nav-link text-white" href="#">Rules</a> -->
          </li>
          <li class="nav-item">
            <a class="nav-link text-white" style="font-size: 18px" href="#">Livescore</a>
          </li>
          <li class="nav-item">
            <!-- <a class="nav-link text-white" href="#">Statistics</a> -->
          </li>
        </ul>
        <div class="tl_logged_out">
          <!-- <a
            name=""
            id=""
            class="btn btn-secondary mr-2"
            href="#"
            role="button"
            >REGISTER</a
          > -->
          <a
            name=""
            id=""
            class="btn btn-outline-secondary text-white mr-2"
            href="#"
            role="button"
            >LOGIN</a
          >

        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {}
</script>

<style>
.tl_logo > a > img {
  flex-shrink: 0;
  flex-grow: 0;
  width: auto;
  height: 40px;
}
</style>
