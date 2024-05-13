<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2>pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
            <div class="card-body">
              <h2>Cari Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>

    <h2 class="mt-5" style="font-family: inter; margin-left: 150px;">STATISTIK</h2>

    <div class="row my-5">
      <div class="col-lg-6">

        <div class="card bg-caripengunjung rounded-5">
          <div class="card-body">
            <div class="text">
              <h1 style="font-size: 110px;">{{ visitor }}</h1>
              <h2>Pengunjung</h2>
            </div>
          </div>
        </div>

      </div>

      <div class="col-lg-6">

        <div class="card bg-caribuku rounded-5">
          <div class="card-body">
            <div class="text">
              <h1 style="font-size: 110px;">{{ book }}</h1>
              <h2>Buku</h2>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
  <div class="c">
    <Chart />
  </div>
</template>
<script setup>
const supabase = useSupabaseClient();
const book = ref(0);
const visitor = ref(0);

const countVisitor = async () => {
  const { data, count } = await supabase
  .from("pengunjung")
  .select("*", {count: "exact"});
  if (data) visitor.value = count;
};
const countBook = async () => {
  const { data, count } = await supabase
  .from("buku")
  .select("*", {count: "exact"});
  if (data) book.value = count;
};

onMounted(() => {
  countVisitor()
  countBook()
})
</script>

<style scoped>
.c {
  width: 80%;
  justify-content: center;
  align-items: center;
}
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242
}
.card.bg-pengunjung {
  background-image: url('../assets/img/k.jpeg');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  opacity: 60%;
}
.card.bg-buku {
  background-image: url('../assets/img/c.jpg');
  background-size: cover;
  opacity: 60%;
}
.card.bg-caripengunjung {
  background-color: #D0DDFF;
  background-position: center center;
}
.card.bg-caribuku {
  background-color: #FFCBCB;
  background-position: center center;
}

.text {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
