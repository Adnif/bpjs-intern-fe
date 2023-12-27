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
                <p>Notifikasi</p>
            </div>
        </div>
        <div class="mt-8">
            <p class="text-[#c7332d] text-[16px] font-bold" >Hari ini</p>
            <ul>
                <li v-for="item in menuItems" :key="item.id" class="py-2 px-4 cursor-pointer ">
                    <div class="w-[316px] h-[65px]  hover:bg-gray-100">
                        <p class="ml-2 text-[15px] font-bold">{{ item.text }}</p> 
                        <p class="ml-2 text-[13px]">{{ item.describe }}</p> 
                    </div>
                </li>
            </ul>
        </div>
        <div class="mt-8">
            <p class="text-[#c7332d] text-[16px] font-bold" >Kemarin</p>
            <ul>
                <li v-for="item in menuItems" :key="item.id" class="py-2 px-4 cursor-pointer ">
                    <div class="w-[316px] h-[65px]  hover:bg-gray-100">
                        <p class="ml-2 text-[15px] font-bold">{{ item.text }}</p> 
                        <p class="ml-2 text-[13px]">{{ item.describe }}</p> 
                    </div>
                </li>
            </ul>
        </div>
        <div class="absolute bottom-0 bg-[#efbf0e] w-[360px] h-[25px] "></div>

    </div>
    
    
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      menuText: "Item",
      menuItems: [
        { id: 1, text: "Item child 1", describe:"Item description 1" },
        { id: 2, text: "Item child 2", describe:"Item description 2" },
        { id: 3, text: "Item child 3", describe:"Item description 3" },
      ],
    };
  },

};
</script>
