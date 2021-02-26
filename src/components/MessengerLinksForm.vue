<template>
  <form class="flex flex-col" @submit.prevent="goToLinks">
    <div class="flex flex-col text-left mb-6">
      <MessengerLinksInput @writeInfo="writeNumber" placeholder="Например: 7 ххх ХХХХХХХ" type="tel">
        <template #name>Номер:</template>
      </MessengerLinksInput>

      <MessengerLinksInput @writeInfo="writeText" value="День добрый, я по поводу..." type="text">
        <template #name>Ваше сообщение:</template>
      </MessengerLinksInput>
    </div>

    <button title="Перейти по сгенерированной ссылке в WhatsUp" type="submit" class="text-white bg-green-500 rounded-md h-8">Перейти</button>
  </form>
</template>

<script>
  import MessengerLinksInput from "./MessengerLinksInput.vue"

  export default {
    name: "MessengerLinksForm",
    components: { MessengerLinksInput },
    data () {
      return {
        number: '',
        text: ''
      }
    },
    methods: {
      writeNumber (number) {
        this.number = number.replace(/[\s|+]/g, '')
      },

      writeText (text) {
        this.text = text
      },

      goToLinks () {
        window.open(`https://api.whatsapp.com/send?phone=${this.number}&text=${this.text}`)
      }
    }
  }
</script>