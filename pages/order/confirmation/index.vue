<script setup>
    const isOpen = ref(false)
</script>
<template>
    <head>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css">
    </head>
    <div class="bg-grey w-[360px] h-[877px] mx-auto">
        <div class="flex space-x-12">
            <a href="/home">
                <div class="rounded-full bg-[#fdca0d] w-[36px] h-[36px] mt-1.5">
                
                </div>
            </a>

            <div class="bg-[#fdca0d] w-[275px] h-[49px] rounded-l-md flex justify-center">
                <p>Pesan Makanan</p>
            </div>
        </div>
        <div class="mt-8">
            <p class="text-[#c7332d]">Informasi Pemesan</p>
            <div class="flex p-12 gap-12 rounded-md border-[#a0fcec] border-2">
                <div class="flex flex-col justify-center w-full">
                    <p class="text-gray-800 font-medium text-base leading-6">Ferry Setiawan</p>
                    <p class="text-gray-800 text-sm leading-6">PSI 2</p>
                    <hr class="border-t-2 border-gray-300 my-4">
                    <p class="text-gray-800 text-base leading-6 justify-center">Detail Pesanan</p>
                    <div class="max-w-md bg-white flex space-x-6 justify-center">
                        <!-- Bagian Nominal (Kiri) -->
                        <div class="">
                            <p class="text-sm">1</p>
                        </div>

                        <!-- Bagian Nama Barang (Tengah) -->
                        <div class="">
                            <p class="text-sm">Contoh Barang</p>
                        </div>

                        <!-- Bagian Harga (Kanan) -->
                        <div class="">
                            <p class="text-sm">20.000</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="flex justify-center mt-4">
                <button label="Open" @click="isOpen = true" type="button" class="w-[200px] bg-[#FDCA0D] text-black py-2 px-4 rounded-md hover:bg-#FDCA0D focus:outline-none focus:bg-[#FDCA0D]">Pesan Sekarang</button>
            </div>
            <div class="flex justify-center mt-2">
                <button type="button" class="w-[200px] border border-[#FDCA0D] text-[#FDCA0D] px-4 py-2 rounded-md hover:bg-[#FDCA0D] hover:text-white focus:outline-none focus:bg-#FDCA0D focus:border-[#FDCA0D] ">Tambah Pesanan</button>
                <UModal v-model="isOpen">
                    <div class="p-4 flex justify-center">
                        <p class="font-bold">Makanan berhasil dipesan</p>
                    </div>
                </UModal>
            </div>
            


        </div>
        <div class="absolute bottom-0 bg-[#efbf0e] w-[360px] h-[25px] "></div>

    </div>
    
    
</template>

<script>
import OrderFrom from "../components/foodform.vue";
export default {

  components:{
    OrderFrom
  }

};

</script>
