<script setup>
import { reactive, ref } from "vue";
import { useRoute, useRouter } from "vue-router";
import { useAuthRepository } from "@/composables";

const repository = useAuthRepository();
const route = useRoute();
const router = useRouter();

const credentials = reactive({
  email: "",
  password: "",
  device_name: "browser",
});

const isLoggingIn = ref(false);
const onSubmit = async () => {
  isLoggingIn.value = true;

  try {
    const { data } = await repository.login(credentials);
    if (data) {
      localStorage.setItem("access_token", data.access_token);
      localStorage.setItem("user", data.user);
      router.replace({ name: "home" });
    }
  } catch (e) {
    console.error(e);
  }

  isLoggingIn.value = false;
};


</script>


<template>
  <main class="grid sm:grid-cols-2 md:grid-cols-8 lg:grid-cols-12 lg:grid-cols-12">
    <section class="sm:col-span-4 relative">
      <form
        method="post"
        :action="route.path"
        class="p-20 my-10"
        @submit.prevent="onSubmit"
      >
        <div class="mb-4">
          <label for="email" class="block mb-2 font-['Poppins'] font-medium">Email</label>
          <input
            v-model="credentials.email"
            type="email"
            required
            placeholder="someone@email.com"
            class="border p-2 w-full bg-gray-50 outline-none focus:ring-4 focus:ring-indigo-400 rounded"
          />
        </div>
        <div class="mb-4">
          <label for="password" class="block mb-2 font-['Poppins'] font-medium">Password</label>
          <input
            v-model="credentials.password"
            type="password"
            required
            class="border p-2 w-full bg-gray-50 outline-none focus:ring-4 focus:ring-indigo-400 rounded"
          />
        </div>
        <button
          type="submit"
          class="bg-blue-600 text-white font-semibold p-2 w-full block hover:bg-blue-800 rounded transition-colors duration-200 select-none"
        >
          Masuk
        </button>
      </form>
    </section>
    <div class="lg:col-span-8">
      <p class="absolute sm:top-52 lg:top-24 text-white z-50 font-['Poppins'] font-semibold 
                tracking-wider w-[66%] text-center text-2xl">
          Review Resto
      </p>
      <p class="absolute sm:top-96 md:top-20 lg:top-32 sm:py-6 lg:py-26 sm:p-36 lg:p-16 text-white z-10 font-['Poppins'] 
      font-medium tracking-wider break-all text-lg">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis eligendi quis, laudantium beatae illo quasi, 
          excepturi fugit, nulla rerum vero inventore. Incidunt temporibus repellat atque recusandae voluptates. 
          Repellendus, distinctio nihil totam et saepe alias, officia repudiandae perferendis doloribus accusamus temporibus.
      </p>
      <div class="bg-black">
        <img src="https://i.pinimg.com/564x/41/5c/62/415c62827ae09a85279d849676560b5c.jpg" 
        class=" sm-h-32 max-h-screen w-full opacity-60" 
        alt="">
      </div>
    </div>
  </main>
</template>