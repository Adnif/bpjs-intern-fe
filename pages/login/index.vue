<script setup>
const router = useRouter()
const showSuccessModal = ref(false)
const showFailedModal = ref(false)

const formData = ref({
  email: '',
  password: '',
})


async function submitForm() {
  try {
    const response = await useFetch('http://localhost:8050/api/v1/user/userLog', {
      method: 'POST',
      body: formData.value
    })

    // Handle success (e.g., display a success message or redirect)
    console.log('Login successful:', response.data);
    console.log('Password:', response.data._rawValue.data.password);
    console.log('Nama:', response.data._rawValue.data.nama);

    const fetchedPassword = response.data._rawValue.data.password;
    const fetchedName = response.data._rawValue.data.nama;

    if(formData.value.password == fetchedPassword){
        showSuccessModal.value = true;
        setTimeout(() => {
            router.push
            ({
                path: "/home",
                query: { name: fetchedName },
                
            })
        }, 2000)
    } else{
        showFailedModal.value = true;
    }
    
  } catch (error) {
    // Handle errors (e.g., display an error message to the user)
    console.error('Login failed:', error)
  }
}
</script>
<template>
    <head>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css">
    </head>
    <div class="bg-[#ffffff] w-[360px] mx-auto">
        <div class="bg-[#fdca0d] w-[200px] h-[36px] rounded-r-md mb-4" >
            <p>
                Waroeng Podjok
            </p>
        </div>
        <div>
            <h2 class="text-2xl font-semibold">Selamat Datang</h2>
            <p class="mb-4">Silahkan login menggunakan email dan password anda</p>
            
                <!-- Alamat Email -->
                <div class="mb-4">
                    <label for="email" class="block text-gray-700 text-sm font-medium mb-2">Alamat Email</label>
                    <input type="email" id="email" name="email" v-model= "formData.email" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
                </div>

                <!-- Password -->
                <div class="mb-2">
                    <label for="password" class="block text-gray-700 text-sm font-medium mb-2">Password</label>
                    <input type="password" id="password" name="password" v-model= "formData.password" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
                </div>

                <div class="mb-4 flex items-center">
                    <input type="checkbox" id="remember_me" name="remember_me" class="mr-2">
                    <label for="remember_me" class="text-gray-700 text-sm">Remember Me</label>
                </div>

                <!-- Tombol Submit -->
                <div class="mb-4">
                    <button @click="submitForm" type="button" class="w-full bg-[#FDCA0D] text-black py-2 px-4 rounded-md hover:bg-#FDCA0D focus:outline-none focus:bg-[#FDCA0D]">Log in</button>
                </div>

                <!-- Pembatas (Divider) -->
                <div class="mb-4 border-b border-gray-300"></div>

                <!-- Tombol "Login with Google" -->
                <div class="mb-6">
                    <button  type="button" class="w-full border border-[#FDCA0D] text-[#FDCA0D] px-4 py-2 rounded-md hover:bg-[#FDCA0D] hover:text-white focus:outline-none focus:bg-#FDCA0D focus:border-[#FDCA0D] "><i class="fab fa-google mr-2"></i>Login with Google</button>
                </div>
            
            <div>
                <p>Belum memiliki akun? <a h f="/" class="font-bold">Daftar</a> </p>
            </div>
            <UModal v-model="showSuccessModal">
                <div class="p-4 flex justify-center">
                    <p class="font-bold">Berhasil Login!</p>
                </div>
            </UModal>
            <UModal v-model="showFailedModal">
                <div class="p-4 flex justify-center">
                    <p class="font-bold">Password Salah!</p>
                </div>
            </UModal>
        </div>
    </div>
</template>
