<template>
    <div class="container">
        <div class="row justify-content-center mt-5">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header">
                        <h3 class="card-title">Users Table</h3>

                        <div class="card-tools">
                            <button class="btn btn-success btn-sm" data-toggle="modal" data-target="#addNew"><i class="fa fa-user-plus white"></i> Add new</button>
                        </div>
                    </div>
                    <!-- /.card-header -->
                    <div class="card-body table-responsive no-padding">
                        <table class="table table-hover">
                            <tbody>
                                <tr>
                                    <th>ID</th>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Type</th>
                                    <th>Modify</th>
                                </tr>
                                <tr>
                                    <td>1</td>
                                    <td>John Doe</td>
                                    <td>11-7-2014</td>
                                    <td><span class="label label-success">Approved</span></td>
                                    <td>
                                        <a href="">
                                            <i class="fa fa-edit blue"></i>
                                        </a>
                                        /
                                        <a href="">
                                            <i class="fa fa-trash red"></i>
                                        </a>
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
            <div class="modal-dialog modal-dialog-centered" role="document">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="addNewLabel">Add New title</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <div class="modal-body">
                        <!-- Name -->
                        <div class="form-group">
                            <input type="text" placeholder="Name" v-model="form.name" id="name" name="name" class="form-control" :class="{ 'is-invalid' : form.errors.has('name') }">
                            <has-error :form="form" field="name"></has-error>
                        </div>
                        <!-- Email -->
                        <div class="form-group">
                            <input type="email" placeholder="Email Address" v-model="form.email" name="email" class="form-control" :class="{ 'is-invalid' : form.errors.has('email') }">
                            <has-error :form="form" field="email"></has-error>
                        </div>
                        <!-- Bio -->
                        <div class="form-group">
                            <textarea type="text" placeholder="Short bio for user (Optional)" v-model="form.bio" name="bio" class="form-control" :class="{ 'is-invalid' : form.errors.has('bio') }"></textarea>
                            <has-error :form="form" field="bio"></has-error>
                        </div>
                        <!-- Type -->
                        <div class="form-group">
                            <select name="type" id="type" v-model="form.type" class="form-control" :class="{ 'is-invalid' : form.errors.has('type')}">
                                <option value="">Select user Role</option>
                                <option value="admin">Admin</option>
                                <option value="user">User</option>
                                <option value="author">Author</option>
                            </select>
                            <has-error :form="form" field="type"></has-error>
                        </div>
                        <!-- Password -->
                        <div class="form-group">
                            <input type="password" id="password" v-model="form.password" name="password" class="form-control" :class="{ 'is-invalid' : form.errors.has('password') }">
                            <has-error :form="form" field="password"></has-error>
                        </div>
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                        <button type="button" class="btn btn-primary">Save changes</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                form: new form ({
                    name: '',
                    email: '',
                    password: '',
                    type: '',
                    bio: '',
                    photo: ''
                })
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
