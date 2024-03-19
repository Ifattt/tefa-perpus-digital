<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-2">
        <div class="card mb-3">
          <div class="card-body">
            <img src="assets/img/perahukertas.jpg" class="cantikituluka" alt="cantikituluka">
          </div>
        </div>
      </div>
      <div class="col-lg-6">
        <div class="col p-5"><h1 style="font-size: 40px;">PERAHU KERTAS</h1></div>
        <h4>Pengarang: Dewi Lestari</h4>
        <h4>Negara: Indonesia</h4>
        <h4>Bahasa: Indonesia</h4>
        <h4>Genre: Fiksi / Novel Remaja</h4>
        <h4>Penerbit: Truedee Books & Bentang Pustaka</h4>
        <h4>Tahun Terbit: 2009</h4>
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
