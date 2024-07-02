<template>
  <div>
      <!-- Modal trigger button -->
  <button
    id="btnopen"
    type="button"
    class="btn btn-primary btn-lg d-none"
    data-bs-toggle="modal"
    data-bs-target="#modalId"
  >
    Open
  </button>
  
  <!-- Modal Body -->
  <!-- if you want to close by clicking outside the modal, delete the last endpoint:data-bs-backdrop and data-bs-keyboard -->
  <div
    class="modal fade"
    id="modalId"
    tabindex="-1"
    data-bs-backdrop="static"
    data-bs-keyboard="false"
    
    role="dialog"
    aria-labelledby="modalTitleId"
    aria-hidden="true"
  >
    <div
      class="modal-dialog modal-dialog-scrollable modal-dialog-centered modal-lg"
      role="document"
    >
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="modalTitleId">
            {{title}}
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">{{desc}}</div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            data-bs-dismiss="modal"
          >
            Fechar
          </button>
          <a :href="src" type="button" class="btn btn-primary">Ir Para o Projeto</a>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
export default {

    props: {

        title: String,
        desc: String,
        src: String


    }

}
</script>

<style>

</style>