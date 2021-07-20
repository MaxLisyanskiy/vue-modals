<template>
  <div class="wrapper">
    <div class="wrapper-content">

      <section>
        <div class="container">

          <h1 class="title">Choose your modal:</h1>
          <button class="btn btnPrimary" @click="modalFirst = !modalFirst">First Modal</button>
          <button class="btn btnPrimary" @click="modalSecond.show = !modalSecond.show">Second Modal</button>

          <!-- first-modal -->
          <Modals
            v-show="modalFirst"
            title="First modal"
            @close="modalFirst = false"
          >
            <div slot="body">
              <br>
              <p>First modal text</p>
              <br>
              <br>
              <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Close</button>
            </div>
          </Modals>

          <!-- second-modal -->
          <Modals
            v-show="modalSecond.show"
            title="Second modal with form"
            @close="modalSecond = false"
          >
            <div slot="body">
              <br>
              <form @submit.prevent="submitSecondForm">
                <label>Name</label>
                <input type="text" required v-model="modalSecond.name">
                <label>Email:</label>
                <input type="text" required v-model="modalSecond.email">
                <button class="btn btnPrimary">Submit</button>
              </form>
              <br>
              <br>
            </div>
          </Modals>

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
      modalFirst: false,
      modalSecond: {
        show: false,
        name: '',
        email: ''
      }
    }
  },
  methods: {
    submitSecondForm() {
      console.log({
        name: this.modalSecond.name,
        email: this.modalSecond.email,
      })
      this.modalSecond.show = false;
      this.modalSecond.name = '';
      this.modalSecond.email = '';
    }
  }
}
</script>
