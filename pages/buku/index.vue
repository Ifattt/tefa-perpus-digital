<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-control rounded-5" placeholder="mau baca apa hari ini?">
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 3</div>
        <div class="row">
          <div class="col-lg-2">
            <div class="card mb-3">
              <nuxt-link to="/buku/buku1">
                <div class="card-body">
                <img src="~/assets/img/cover1.jpg" class="cover" alt="cover 1">
              </div>
              </nuxt-link>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <nuxt-link to="/buku/buku2">
                <div class="card-body">
                  <img src="~/assets/img/cover2.jpg" class="cover" alt="cover 2">
                </div>
              </nuxt-link>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <nuxt-link to="/buku/buku3">
                <div class="card-body">
                  <img src="assets/img/cover3.jpeg" class="cover" alt="cover 3">
                </div>
              </nuxt-link>
            </div>
          </div>
        </div>
        <nuxt-link to="../">
        <button type="button" class="btn btn-secondary" style="border-radius: 25px; font-size: 25px; margin-top: 25px;">kembali</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-body {
  width: 100%;
  height: 20em;
  padding: 5;
}
.cover {
  width: 80%;
}
</style>