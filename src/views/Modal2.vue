<template>
  <div class="container mt-5">
    <b-button v-b-modal.modal-1>Launch demo modal</b-button>

    <b-modal id="modal-1" title="BootstrapVue">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
    <div class="shadow-none p-3 mb-5 bg-light rounded">No shadow</div>
    <div class="shadow-sm p-3 mb-5 bg-white rounded">Small shadow</div>
    <div class="shadow p-3 mb-5 bg-white rounded">Regular shadow</div>
    <div class="shadow-lg p-3 mb-5 bg-white rounded">Larger shadow</div>

    <br />
    <p class="user-select-all">
      This paragraph will be entirely selected when clicked by the user.
    </p>
    <p class="user-select-auto">
      This paragraph has the default select behavior.
    </p>
    <p class="user-select-none">
      This paragraph will not be selectable when clicked by the user.
    </p>
    <table class="table table-hover">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Handle</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>
