<template>
  <div class="modal fade" id="formModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="exampleModalLabel">
            <slot name="header"></slot>
          </h1>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <!-- <CarForm /> -->
          <slot name="body"></slot>
        </div>

      </div>
    </div>
  </div>
</template>


<script>
export default {

  setup() {
    return {};
  },
}
</script>


<style lang="scss" scoped></style>