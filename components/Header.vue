<template>
  <header class="bg-slate-950 text-white py-6 shadow-lg">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl">Nail Design Studio</h1>
      <nav>
        <ul class="flex space-x-6">
          <li>
            <a
              href="/"
              class="text-sm font-medium hover:text-yellow-400 transition"
            >
              Home
            </a>
          </li>
          <li>
            <a
              @click="showModal = true"
              class="text-sm font-medium hover:text-yellow-400 transition"
            >
              Login
            </a>
          </li>
          <li>
            <a
              @click="showCadastroModal = true"
              class="text-sm font-medium hover:text-yellow-400 transition"
            >
              Cadastro
            </a>
          </li>
          <li>
            <a
              href="/contact"
              class="text-sm font-medium hover:text-yellow-400 transition"
            >
              Contato
            </a>
          </li>
        </ul>
      </nav>
      <LoginModal v-if="showModal" :isVisible="showModal" @close="showModal = false" />
      <CadastroModal v-if="showCadastroModal" :isOpen="showCadastroModal" @close="showCadastroModal = false" />
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      showModal: false,
      showCadastroModal: false
    };
  },
};
</script>
