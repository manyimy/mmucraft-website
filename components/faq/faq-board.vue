<template>
  <MCBoard>
    <MCTitle class="mt-4" style="text-shadow: 2px 6px 3px #000000;">
      {{ sectionTitle }}
    </MCTitle>
    <hr>
    <div v-for="(faq, key) in faqs" :key="`faq-${key}`">
      <div class="px-4 py-0">
        <FaqCard
          :id="`faq-card-${key}`"
          :question="faq.question"
          :answer="faq.answer"
          accordion="faq-accordion"
        />
      </div>
      <hr>
    </div>
  </MCBoard>
</template>

<script>
import { faqs } from '~/assets/json/faqs.json'
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'
import FaqCard from '~/components/faq/faq-card'

export default {
  components: {
    MCBoard,
    MCTitle,
    FaqCard
  },
  data: () => {
    return {
      faqs,
      sectionTitle: 'Frequently Asked Questions'
    }
  }
}
</script>

<style>

</style>
