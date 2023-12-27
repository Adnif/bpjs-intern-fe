<template>
    <div class="dropdown">
        <div @click="toggleDropdown" class="flex items-center cursor-pointer space-x-[285px]">
            <span class="text-2xl text-[#cc5853]">{{ menuText }}</span>
            <i :class="['ml-2', isOpen ? 'fas fa-caret-up' : 'fas fa-caret-down']"></i>
        </div>

        <div v-if="isOpen" @click="closeDropdown" class="mt-2">
            <ul class="bg-white rounded-md">
                <li v-for="item in menuItems" :key="item.id" class="py-2 px-4 cursor-pointer ">
                    <div class="w-[316px] h-[65px] bg-[#fff7f7] rounded-md border-l-4 border-[#cc5853] hover:bg-gray-100">
                        <p class="ml-2 text-[15px] font-bold">{{ item.text }}</p> 
                        <p class="ml-2 text-[13px]">{{ item.describe }}</p> 
                 
                    </div>
                
                </li>
            </ul>
        </div>
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
  methods: {
    toggleDropdown() {
      this.isOpen = !this.isOpen;
    },
    closeDropdown() {
      this.isOpen = false;
    },
  },
};
</script>