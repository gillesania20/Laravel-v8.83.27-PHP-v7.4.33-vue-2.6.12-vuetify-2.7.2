<template>
    <div>
        <h1>Job Posting Lists</h1>
        <table class="table table-hover">
            <thead>
                <tr>
                    <th>Job Name</th>
                    <th>Job Description</th>
                    <th>Vacants</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Sr Programmer</td>
                    <td>Lead developer</td>
                    <td>2</td>
                    <td>
                        <button class="btn btn-secondary">
                            <i class="fa fa-edit"></i>
                        </button>
                        <button class="btn btn-danger">
                            <i class="fa fa-trash"></i>
                        </button>
                        <v-btn
                        elevation="2"
                        >VUETIFY BTN</v-btn>
                    </td>
                </tr>
            </tbody>
            <tfoot>
                <tr>
                    <td>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Input Job Name"
                                v-model="form.job_name">
                        </div>
                    </td>
                    <td>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Input Job Description"
                                v-model="form.job_description">
                        </div>
                    </td>
                    <td>
                        <div class="form-group">
                            <input type="number" class="form-control" placeholder="Input Vacants"
                                v-model="form.vacants">
                        </div>
                    </td>
                    <td>
                        <div class="form-group">
                            <button class="btn btn-primary" @click="submit()"><i class="fa fa-plus"></i></button>
                        </div>
                    </td>
                </tr>
            </tfoot>
        </table>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                form: {
                    job_name: null,
                    job_description: null,
                    vacants: 0
                }
            }
        },
        methods: {
            submit() {
                axios.post('/job_posting', {
                    job_name: this.form.job_name,
                    job_description: this.form.job_description,
                    vacants: this.form.vacants
                })
                .then(()=>{
                    alert('success');
                })
                .catch(()=>{
                    alert('error');
                });
            }
        }
    }
</script>