<template>
  <div class="wrapper">
    <div class="wrapper-content">

      <section>
        <div class="container">

          <h1 class="title">Choose your modal:</h1>
          <button class="btn btnPrimary" @click="modalFirst = !modalFirst">First Modal</button>

          <!-- first-modal -->
          <Modals
            v-if="modalFirst"
            title="First modal"
            @close="modalFirst = !modalFirst"
          />

        </div>
      </section>

    </div>
  </div>
</template>

<script>
import Modals from '@/components/Modal.vue'

export default {
  components: { Modals },
  data () {
    return {
      modalFirst: false
    }
  },
  methods: {}
}
</script>
