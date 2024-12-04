<template>
  <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50">
    <div class="bg-white rounded-lg w-96 p-6 relative">
      <button
        class="absolute top-3 right-3 text-gray-500 hover:text-gray-800"
        @click="closeModal"
      >
        &times;
      </button>
      <h2 class="text-xl font-bold mb-4 text-gray-700 text-center">Cadastrar-se</h2>
      <form @submit.prevent="handleSubmit">
        <div class="mb-4">
          <label for="name" class="block text-gray-700 font-medium">Nome</label>
          <input
            type="text"
            id="name"
            v-model="formData.name"
            placeholder="Digite seu nome"
            class="mt-1 w-full p-2 border rounded-md text-gray-800 focus:ring focus:ring-indigo-500"
            required
          />
        </div>
        <div class="mb-4">
          <label for="email" class="block text-gray-700 font-medium">E-mail</label>
          <input
            type="email"
            id="email"
            v-model="formData.email"
            placeholder="Digite seu e-mail"
            class="mt-1 w-full p-2 border rounded-md text-gray-800 focus:ring focus:ring-indigo-500"
            required
          />
        </div>
        <div class="mb-4">
          <label for="phone" class="block text-gray-700 font-medium">Telefone</label>
          <input
            type="tel"
            id="phone"
            v-model="formData.phone"
            placeholder="Digite seu telefone"
            class="mt-1 w-full p-2 border rounded-md text-gray-800 focus:ring focus:ring-indigo-500"
            required
          />
        </div>
        <div class="mb-4">
          <label for="password" class="block text-gray-700 font-medium">Senha</label>
          <input
            type="password"
            id="password"
            v-model="formData.password"
            placeholder="Digite sua senha"
            class="mt-1 w-full p-2 border rounded-md text-gray-800 focus:ring focus:ring-indigo-500"
            required
          />
        </div>
        <button
          type="submit"
          class="w-full bg-indigo-600 text-white py-2 rounded-md hover:bg-indigo-700 focus:outline-none"
        >
          Cadastrar
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      formData: {
        name: '',
        email: '',
        phone: '',
        password: '',
      },
    };
  },
  methods: {
    closeModal() {
      this.$emit('close');
    },
    handleSubmit() {
      console.log('Dados enviados:', this.formData);
      alert('Cadastro realizado com sucesso!');
      this.closeModal();
    },
  },
};
</script>

