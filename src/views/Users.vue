<template>
  <div>
    <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
    </base-header>
    <div class="container-fluid mt--7">
      <div class="row">
        <div class="col">
          <div class="card shadow" :class="type === 'dark' ? 'bg-default' : ''">
            <div
              class="card-header border-0"
              :class="type === 'dark' ? 'bg-transparent' : ''"
            >
              <div class="row align-items-center">
                <div class="col">
                  <h3 class="mb-0" :class="type === 'dark' ? 'text-white' : ''">
                    Users
                  </h3>
                </div>
                <!-- <div class="col text-right">
                  <b-button variant="primary" size="sm"
                    ><i class="fa fa-plus mr-2"></i>Add</b-button
                  >
                </div> -->
              </div>
            </div>

            <div class="table-responsive">
              <table class="table align-items-center table-flush">
                <thead>
                  <tr>
                    <th>Username</th>
                    <th>Email</th>
                    <th>Actions</th>
                    <th></th>
                  </tr>
                </thead>

                <tbody>
                  <tr>
                    <td>Demo</td>
                    <td>Demo@gmail.com</td>
                    <td>
                      <b-btn-group>
                        <b-button
                          variant="danger"
                          size="sm"
                          title="Block User"
                          v-b-modal.modal-1
                          @click="id== null ? id = 1 : id++"
                          ><i class="fa fa-ban"></i
                        ></b-button>
                      </b-btn-group>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>

            <!-- <div class="card-footer d-flex justify-content-end"
         :class="type === 'dark' ? 'bg-transparent': ''">
      <base-pagination total="30"></base-pagination>
    </div> -->
          </div>
        </div>
      </div>
    </div>
    <b-modal centered id="modal-1" title="Confirmation" hide-footer>
      <p>Do you really want to block user {{id}}?</p>
      <div class="d-flex justify-content-end">
          <b-button variant="danger" @click="$bvModal.hide('modal-1')">Cancel</b-button>
          <b-button variant="success" @click="$bvModal.hide('modal-1')">Yes</b-button>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "users",
  data(){
      return{
          id:null,
      }
  }
};
</script>

<style scoped>
</style>