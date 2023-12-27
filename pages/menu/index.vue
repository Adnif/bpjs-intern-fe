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

            <div class="bg-[#fdca0d] w-[275px] h-[49px] rounded-l-md">
                <p>Pilih makanan kamu</p>
            </div>
        </div>
        <div class="mt-8 space-y-4">
            <!-- Pembatas (Divider) -->
            <div class="mb-4 border-b border-gray-300"></div>
            <dropdown />
            <!-- Pembatas (Divider) -->
            <div class="mb-4 border-b border-gray-300"></div>
            <dropdown />
            <!-- Pembatas (Divider) -->
            <div class="mb-4 border-b border-gray-300"></div>
            <dropdown />
            <!-- Pembatas (Divider) -->
            <div class="mb-4 border-b border-gray-300"></div>
        </div>
        <div class="absolute bottom-0 bg-[#efbf0e] w-[360px] h-[25px] "></div>

    </div>
    
    
</template>

<script>
import Dropdown from "../components/dropdown.vue";

export default {
  components: {
    Dropdown,
  },
};
</script>
