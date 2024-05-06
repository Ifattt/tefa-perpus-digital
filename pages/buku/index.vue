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
          <div v-for="(book, i) in books " :key="i" class="col-lg-2">
            <div class="card mb-3">
              <nuxt-link to="/buku/buku1">
                <div class="card-body">
                  <img :src="book.cover" class="cover" alt="cover 1">
                </div>
              </nuxt-link>
            </div>
          </div>
        </div>
        <nuxt-link to="../">
          <button type="button" class="btn btn-secondary"
            style="border-radius: 25px; font-size: 25px; margin-top: 25px;">kembali</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script setup>
const supabase = useSupabaseClient()

const books = ref([])
const keyword = ref("")
const getBooks = async () => {
  const { data, error } = await supabase.from('buku').select(`*, kategori(*)`)
  .like('judul', '%${keyword.value}');
  if(data) books.value = data
}
onMounted(() => {
  getBooks()
})
</script>

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