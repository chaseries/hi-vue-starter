<template>
  <div class="modal-dummy">
    <transition appear name="trans-modal-dummy">
      <div v-if="open">
        <div>Dummy modal component</div>
        <button @click="modalClose">Close modal</button>
      </div>
    </transition>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";


export default {
  name: "modal-dummy",
  methods: {
    ...mapActions({
      modalClose: "modal/close"
    })
  },
  computed: {
    ...mapState({
      open: state => state.modal.open
    })
  }
};
</script>

<style lang="sass">

.modal-dummy
  color: white

.trans-modal-dummy-enter-active
  opacity: 1
  transition: opacity 0.2s linear 0.35s

.trans-modal-dummy-enter
  opacity: 0

.trans-modal-dummy-leave-active
  opacity: 0
  transition: opacity 0.35s linear
</style>

