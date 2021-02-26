<template>
  <div class="green h-screen w-screen flex flex-col items-center justify-center">
    <section class="container-sm design-container rounded-md bg-gray-100 p-12">
      <h1 class="text-4xl mb-10">Конструктор ссылок</h1>
      <MessengerLinksForm/>
    </section>
  </div>
</template>

<script>
  import MessengerLinksForm from "./components/MessengerLinksForm.vue"

  export default {
    components: { MessengerLinksForm }
  }
</script>

<style scoped>
  .green {
    background: hsl(141, 28%, 84%);
  }

  .design-container {
    border-radius: 50px;
    background: hsl(141, 28%, 84%);
    box-shadow:  20px 20px 0px hsl(139, 13%, 72%),
    -20px -20px 0px hsl(147, 100%, 96%);
  }
</style>