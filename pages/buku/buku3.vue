<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-2">
        <div class="card mb-3">
          <div class="card-body">
            <img src="assets/img/pulangtereliye.jpeg" class="pulang" alt="pulang">
          </div>
        </div>
      </div>
      <div class="col-lg-6">
        <div class="col p-5"><h1 style="font-size: 40px;">Pulang</h1></div>
        <h4>Pengarang: Tere Liye</h4>
        <h4>Negara: Indonesia</h4>
        <h4>Bahasa: Indonesia</h4>
        <h4>Genre: Fiksi </h4>
        <h4>Penerbit: Sabak Grip Nusantara</h4>
        <h4>Tahun Terbit: 2020</h4>
      </div>
      <nuxt-link to="/buku">
        <button type="button" class="btn btn-dark btn-lg form-select rounded">KEMBALI</button>
      </nuxt-link>
    </div>
  </div>
</template>

<style scoped>
.cover{
  height: 300px;
  width: 200px;
}
.card.mb-3 {
  margin-top: 50px;
  margin-left: 20px;
  height: 340px;
  width: 235px;
}
h3 {
  margin-top: 50px;
  margin-left: 20px;
}
img {
height: 300px;
width: 200px;
}
</style>
