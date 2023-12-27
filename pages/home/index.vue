<script setup>
const route = useRoute();
const name = route.query.name;

console.log('nama: ', route.query)
</script>

<template>
    <head>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css">
    </head>
    <div class="bg-[#ffffff] w-[360px] mx-auto">
        <div class="bg-[#cc443e] h-[52px]" >
            <p class="font-semibold">
                Waroeng Podjok
            </p>
        </div>
        <div class="bg-[#fdca0d] h-[173px]">
            <div class="ml-6 pt-6">
                <p class="font-semibold">Halo, {{ name }}</p>      
                <p class="text-[32px] font-semibold">Ingin Makan Apa Hari Ini? </p>
            </div>
            
        </div>
        <div class="flex justify-center space-x-6 mt-6">
            <a href="/menu">
                <div class="bg-[#fff3f3] h-[144px] w-[144px] rounded-md text-center" >
                    <p class="text-[16px] font-semibold">
                        List Makanan                  
                    </p>
                    <p class="text-[13px]">
                        Pesan sekarang untuk diantarkan
                    </p>
                </div>
            </a>
            <a href="/order">
            <div class="bg-[#fff3f3] h-[144px] w-[144px] rounded-md text-center">
                <p class="text-[16px] font-semibold">
                    Pesan Makanan
                </p>
                <p class="text-[13px]">
                    Pesan sekarang untuk diantarkan
                </p>
            </div>        
            </a>

        </div>
        <div class="absolute bottom-0 bg-[#efbf0e] w-[360px] h-[25px] "></div>

    </div>
    
</template>