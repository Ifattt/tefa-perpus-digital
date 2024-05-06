<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI BUKU KUNJUNGAN</h2>
        <form @submit.prevent="kirimData">
          <div class="mb-3">
            <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5" placeholder="NAMA...">
          </div>
          <div class="mb-3">
            <select v-model="form.keanggotaan" class="form-control form-control-lg form-select rounded-5"
              placeholder="KEANGGOTAAN">
              <option value="">KATEGORI</option>
              <option value="Siswa">Siswa</option>
              <option value="Guru">Guru</option>
              <option value="Staf">Staf</option>
              <option value="Umum">Umum</option>
            </select>
          </div>
          <div class="mb-3">
            <div class="row">
              <div class="col md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                  <option value="Umum">Umum</option>
                </select>
              </div>
              <div class="col md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">JURUSAN</option>
                  <option value="pplg">PPLG</option>
                  <option value="TJKT">TJKT</option>
                  <option value="TSM">TSM</option>
                  <option value="UMUM">DKV</option>
                  <option value="TOI">TOI</option>
                </select>
              </div>
              <div class="col md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">KELAS</option>
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
                  <option value="4">4</option>
                </select>
              </div>
            </div>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEPERLUAN</option>
              <option value="Baca">Baca Buku</option>
              <option value="Pinjam">Pinjam Buku</option>
              <option value="Kembalikan">Kembalikan Buku</option>
            </select>
          </div>
          <nuxt-link to="/pengunjung">
            <button type="button" class="btn btn-secondary"
              style="border-radius: 25px; font-size: 25px;margin-bottom: 20px;">KIRIM</button>
            <br>
          </nuxt-link>
          <nuxt-link to="../">
            <button type="button" class="btn btn-secondary" style="border-radius: 25px; font-size: 25px;">back</button>
          </nuxt-link>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const members = ref([])
const objectives = ref([])

const form = ref({
  nama: "",
  keanggotaan: "",
  tingkat: "",
  jurusan: "",
  kelas: "",
  keperluan: "",

})
const kirimData = async () => {
  const { error } = await supabase.from('pengunjung').insert([form.value])
  if (!error) navigateTo('/pengunjung')
}

const getKeanggotaan = async () => {
  const { data, error } = await supabase.from('keanggotaan').select("*");
  if (data) members.value = data
}
const getKeperluan = async () => {
  const { data, error } = await supabase.from('keperluan').select("*");
  if (data) members.value = data
}

onMounted(() => {
  getKategori
  getKeperluan
})     
</script>
