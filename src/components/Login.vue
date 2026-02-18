<template>
  <div class="flex h-screen">

    <!-- LEFT SECTION -->
    <div class="hidden md:flex w-1/2 bg-purple-100 flex-col justify-center p-12">

      <!-- Logo -->
      <div class="flex items-center gap-2 mb-2">
        <img 
          src="/logo.png"
          alt="Logo"
          class="w-40 h-40"
        />
       
      </div>

      <!-- Side Image -->
      <img 
        src="/sideImg.png"
        alt="Team Illustration"
        class="rounded-xl shadow-lg"
      />

      <h2 class="text-[#61227D] lora text-center font-semibold text-lg my-2">
        Team Achieve
      </h2>

      <p class="text-gray-600 lora text-center">
        Your perfect solution for funding your desires
      </p>
    </div>


    <!-- RIGHT SECTION -->
    <div class="w-full md:w-1/2 bg-[#FCFCFC]
 flex items-center justify-center px-4">

      <div class="w-full    md:px-10 px-2 ">
 <div class="flex md:hidden justify-center  items-center ">
        <img 
          src="/logo.png"
          alt="Logo"
          class="w-40 h-40"
        />
       
      </div>
        <h2 class="text-2xl text-center lora font-bold text-[#61227D] mb-2">
          Welcome Back
        </h2>

        <p class="text-gray-500 noto-sans text-center mb-6 text-sm">
          Enter your email address and password to access your account.
        </p>

        <!-- Email -->
        <div class="mb-4 noto-sans">
          <label class="block text-sm text-[#3E3E3E]
 font-medium mb-1">
            Email Address <span class="text-red-500">*</span>
          </label>
          <input
            type="email"
            v-model="email"
            placeholder="Enter your email"
            class="w-full border border-[#C6C6C6] bg-[#FFFFFF] rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[#61227D]"
          />
        </div>

        <!-- Password -->
        <div class="mb-4">
          <label class="block text-sm text-[#3E3E3E] font-medium mb-1">
            Password <span class="text-red-500">*</span>
          </label>
          <div class="w-full flex border border-[#C6C6C6] rounded-lg focus-within:ring-2 focus-within:ring-[#61227D]">

  <input
    :type="showPassword ? 'text' : 'password'"
    v-model="password"
    placeholder="Enter your password"
    class="w-full px-3 py-2 border-0 bg-[#FFFFFF] outline-none rounded-l-lg"
  />

  <button
    type="button"
    @click="togglePassword"
    class="w-14 flex items-center cursor-pointer  justify-center border-l border-[#C6C6C6] bg-gray-100 rounded-tr-lg rounded-br-lg"
  >
    <Eye v-if="showPassword" class="text-gray-500"  :size="20" />
    <EyeOff v-else class="text-gray-500"  :size="20" />
  </button>

</div>

        </div>

        <!-- Remember + Forgot -->
        <div class="flex justify-between items-center mb-6 text-sm">
          <label class="flex items-center text-[#3E3E3E] gap-2">
            <input type="checkbox" v-model="remember" />
            Remember me
          </label>

          <a href="#" class="text-[#61227D] hover:underline">
            Forgot Password?
          </a>
        </div>

        <!-- Button -->
        <button
          @click="login"
          class="w-full bg-[#61227D] text-white py-2 cursor-pointer rounded-lg hover:opacity-90 transition"
        >
          Sign in
        </button>

        <!-- Bottom Text -->
        <p class="text-sm text-center mt-4">
          Don’t have an account?
          <span class="text-[#61227D] font-semibold cursor-pointer">
            Sign up
          </span>
        </p>

      </div>

    </div>

  </div>
</template>


<script setup>
import { ref } from "vue"
import { Eye, EyeOff } from 'lucide-vue-next';

const email = ref("")
const password = ref("")
const remember = ref(false)
const showPassword = ref(false)

const togglePassword = () => {
  showPassword.value = !showPassword.value
}
const login = () => {
  if (!email.value || !password.value) {
    alert("Please fill in all fields")
    return
  }

  alert("Login successful!")
}
</script>
