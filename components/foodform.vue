<template>
    <div>
      <form @submit.prevent="submitForm">
        <!-- Nama -->
        <div class="mb-4">
          <label for="nama" class="block text-gray-700 text-sm font-medium">Nama</label>
          <input v-model="nama" type="text" id="nama" name="nama" class="mt-1 p-2 border rounded-md w-full">
        </div>
  
        <!-- Divisi -->
        <div class="mb-4">
          <label for="divisi" class="block text-gray-700 text-sm font-medium">Divisi</label>
          <input v-model="divisi" type="text" id="divisi" name="divisi" class="mt-1 p-2 border rounded-md w-full">
        </div>
  
        <!-- Kategori Makanan -->
        <div class="mb-4">
          <label for="kategori" class="block text-gray-700 text-sm font-medium">Kategori Makanan</label>
          <select v-model="kategori" @change="handleKategoriChange" id="kategori" name="kategori" class="mt-1 p-2 border rounded-md w-full">
            <option value="">Pilih Kategori</option>
            <option value="makananRingan">Makanan Ringan</option>
            <option value="makananBerat">Makanan Berat</option>
          </select>
        </div>
  
        <!-- Formulir tambahan yang muncul jika kategori dipilih -->
        <div v-if="kategori">
          <!-- Makanan -->
          <div class="mb-4">
            <label for="makanan" class="block text-gray-700 text-sm font-medium">Makanan</label>
            <select v-model="makanan" id="makanan" name="makanan" class="mt-1 p-2 border rounded-md w-full">
              <option value="">Pilih Makanan</option>
              <option v-if="kategori === 'makananRingan'" value="keripik">Keripik</option>
              <option v-if="kategori === 'makananBerat'" value="nasiGoreng">Nasi Goreng</option>
            </select>
          </div>
  
          <!-- Catatan -->
          <div class="mb-4">
            <label for="catatan" class="block text-gray-700 text-sm font-medium">Catatan</label>
            <textarea v-model="catatan" id="catatan" name="catatan" rows="3" class="mt-1 p-2 border rounded-md w-full"></textarea>
          </div>
        </div>
        <div class="flex justify-center">
          <NuxtLink to="/order/confirmation">
            <button type="submit" class="bg-[#fdca0d] text-black font-bold py-2 px-12 rounded-md">Konfirmasi</button>
          </NuxtLink>
        </div>
  
        
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        nama: '',
        divisi: '',
        kategori: '',
        makanan: '',
        catatan: '',
      };
    },
    methods: {
      handleKategoriChange() {
        // Reset nilai makanan dan catatan ketika kategori berubah
        this.makanan = '';
        this.catatan = '';
      },
      submitForm() {
        // Lakukan logika pengiriman formulir atau sesuaikan sesuai kebutuhan
        console.log('Formulir Dikirim', this.nama, this.divisi, this.kategori, this.makanan, this.catatan);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Gaya CSS Tailwind atau kustom di sini */
  </style>
  