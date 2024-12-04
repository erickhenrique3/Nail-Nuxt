<template>
  <div
    v-if="isVisible"
    class="fixed inset-0 bg-gray-800 bg-opacity-75 flex items-center justify-center z-50 "
  >
    <div
      class="bg-white rounded-lg w-96 p-6 relative shadow-lg transform transition-all"
    >
      <!-- Botão de Fechar -->
      <button
        @click="closeModal"
        class="absolute top-2 right-2 text-gray-500 hover:text-gray-700"
      >
        <span class="text-2xl">&times;</span>
      </button>

      <!-- Título -->
      <h2 class="text-xl font-bold text-center mb-4 text-gray-700">Login</h2>

      <!-- Formulário -->
      <form @submit.prevent="submitLogin">
        <div class="mb-4">
          <label for="email" class="block text-sm font-medium text-gray-700">
            E-mail
          </label>
          <input
            type="email"
            id="email"
            v-model="email"
            placeholder="Digite seu e-mail"
            autocomplete="off"
            class="mt-1 w-full p-2 border rounded-md text-gray-700"
          />
        </div>
        <div class="mb-4">
          <label for="password" class="block text-sm font-medium text-gray-700">
            Senha
          </label>
          <input
            type="password"
            id="password"
            v-model="password"
            placeholder="Digite sua senha"
            autocomplete="off"
            class="mt-1 w-full p-2 border rounded-md text-gray-700"
          />
        </div>

        <!-- Botões -->
        <div class="flex items-center justify-between">
          <button
            type="submit"
            class="bg-indigo-600 text-white px-4 py-2 rounded-md hover:bg-natural-700 transition"
          >
            Entrar
          </button>
          <button
            type="button"
            @click="closeModal"
            class="text-gray-500 hover:text-gray-700 transition"
          >
            Cancelar
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isVisible: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
    submitLogin() {
      console.log("Email:", this.email, "Senha:", this.password);
      this.closeModal();
    },
  },
};
</script>
