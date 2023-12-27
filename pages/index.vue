<script setup>
const router = useRouter()
const showSuccessModal = ref(false)

const formData = ref({
  nama: '',
  password: '',
  email: '',
  noHp: '',
  rolekode: 'PM'
})


async function submitForm() {
  try {
    const response = await useFetch('http://localhost:8050/api/v1/user/save', {
      method: 'POST',
      body: formData.value
    })

    // Handle success (e.g., display a success message or redirect)
    console.log('Registration successful:', response.data);
    showSuccessModal.value = true;
    setTimeout(() => {
        router.push
        ({
            path: "/login"
        })
    }, 2000)
    
  } catch (error) {
    // Handle errors (e.g., display an error message to the user)
    console.error('Registration failed:', error)
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
            <h2 class="text-2xl font-semibold">Buat Akun</h2>
            <p class="mb-4">Untuk memiliki akun, silahkan mendaftarkan diri Anda</p>

            <!-- Nama Lengkap -->
            <div class="mb-4">
                <label for="nama_lengkap" class="block text-gray-700 text-sm font-medium mb-2">Nama Lengkap</label>
                <input type="text" id="nama_lengkap" name="nama_lengkap" v-model="formData.nama" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
            </div>

            <!-- Alamat Email -->
            <div class="mb-4">
                <label for="email" class="block text-gray-700 text-sm font-medium mb-2">Alamat Email</label>
                <input type="email" id="email" name="email" v-model="formData.email" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
            </div>

            <!-- Nomor Telepon -->
            <div class="mb-4">
                <label for="nomor_telepon" class="block text-gray-700 text-sm font-medium mb-2">Nomor Telepon</label>
                <input type="tel" id="nomor_telepon" name="nomor_telepon" v-model="formData.noHp" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
            </div>

            <!-- Password -->
            <div class="mb-2">
                <label for="password" class="block text-gray-700 text-sm font-medium mb-2">Password</label>
                <input type="password" id="password" name="password" v-model="formData.password" class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500">
            </div>

            <div class="mb-4 flex items-center">
                <input type="checkbox" id="remember_me" name="remember_me" class="mr-2">
                <label for="remember_me" class="text-gray-700 text-sm">Remember Me</label>
            </div>

            <!-- Tombol Submit -->
            <div class="mb-4">
                <form @click="submitForm">
                    <button type="button" class="w-full bg-[#FDCA0D] text-black py-2 px-4 rounded-md hover:bg-#FDCA0D focus:outline-none focus:bg-[#FDCA0D]">Log in</button>
                </form>
            </div>

            <!-- Pembatas (Divider) -->
            <div class="mb-4 border-b border-gray-300"></div>

            <!-- Tombol "Login with Google" -->
            <div class="mb-6">
                
                    <button type="button" class="w-full border border-[#FDCA0D] text-[#FDCA0D] px-4 py-2 rounded-md hover:bg-[#FDCA0D] hover:text-white focus:outline-none focus:bg-#FDCA0D focus:border-[#FDCA0D] "><i class="fab fa-google mr-2"></i>Login with Google</button>
                
            </div>
            <div>
                <p>Sudah memiliki akun? <a href="/login" class="font-bold">Login</a> </p>
            </div>
            <UModal v-model="showSuccessModal">
                <div class="p-4 flex justify-center">
                    <p class="font-bold">Berhasil Registrasi!</p>
                </div>
            </UModal>
        </div>
    </div>
</template>