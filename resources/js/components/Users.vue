<template>
    <div class="container">
        <div class="row mt-5">
          <div class="col-md-12">
            <div class="card">
              <div class="card-header">
                <h3 class="card-title">User Table</h3>

                <div class="card-tools">
                  <button class="btn btn-success" data-toggle="modal" data-target="#addNew">Add new user   <i class="fas fa-user-plus fa-fw"></i> </button>
                </div>
              </div>
              <!-- /.card-header -->
              <div class="card-body table-responsive p-0">
                <table class="table table-hover text-nowrap">
                  <thead>
                    <tr>
                      <th>ID</th>
                      <th>User</th>
                      <th>Email</th>
                      <th>Type</th>
                      <th>Edit</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>183</td>
                      <td>John Doe</td>
                      <td>11-7-2014</td>
                      <td><span class="tag tag-success">Approved</span></td>
                      <td>
                          <a href="#"> </a>
                          <i class="fa fa-edit"></i>
                            /
                            <a href="#"> </a>
                          <i class="fa fa-trash"></i>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>
              <!-- /.card-body -->
            </div>
            <!-- /.card -->
          </div>
        </div>
        <!-- Modal -->
        <div class="modal fade" id="addNew" tabindex="-1" role="dialog" aria-labelledby="addNewLabel" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered">
                <div class="modal-content">
                   <div class="modal-header">
                      <h5 class="modal-title" id="addNewLabel">Add New User </h5>
                      <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                      <span aria-hidden="true">&times;</span>
                    </button>
      </div>


      <div class="modal-body">
        <div class="form-group">
            <input v-model="form.name" type="text" name="name" placeholder="Enter name"
                 class="form-control" :class="{ 'is-invalid': form.errors.has('name') }">
            <has-error :form="form" field="name"></has-error>
        </div>

        <div class="form-group">
            <input v-model="form.email" type="email" name="email" placeholder="Enter email"
                 class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
            <has-error :form="form" field="email"></has-error>
        </div>

        <div class="form-group">
            <textarea v-model="form.bio" type="bio" name="bio" placeholder="Enter bio for user (optional)"
                 class="form-control" :class="{ 'is-invalid': form.errors.has('bio') }">
            <has-error :form="form" field="bio"></has-error>
        </div>

        <div class="form-group">
            <select v-model="form.type" id="type" name="type" 
                 class="form-control" :class="{ 'is-invalid': form.errors.has('type') }">
                <option value="">Select User Role</option>
                <option value="admin">Admin</option>
                <option value="user">Standard</option>
                <option value="author">Author</option>
            <has-error :form="form" field="type"></has-error>
        </div>

        <div class="form-group">
            <input v-model="form.password" type="password" name="password" placeholder="Enter password"
                 class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
            <has-error :form="form" field="password"></has-error>
        </div>

      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Add</button>
      </div>

    </div>
  </div>
</div>
    </div>
</template>

<script>
import Form from 'vform'; 
    export default {
         data () {
    return {
      // Create a new form instance
      form: new Form({
        name: '',
        email:'',
        email_verified_at:'',
        password: ''
      })
    }
  },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
