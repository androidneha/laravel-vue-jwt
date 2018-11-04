<template>
    <div class="login row justify-content-center">
        <div class="col-md-4 px-lg-5">
            <div class="card mt-5">
                <div class="card-header bg-dark text-white">Login</div>
                <div class="card-body px-5">
                    <form @submit.prevent="authenticate">
                        <div class="form-group row">
                            <label>Email:</label>
                            <input type="email" v-model="form.email" class="form-control" placeholder="Email Address">
                        </div>
                        <div class="form-group row">
                            <label>Password:</label>
                            <input type="password" v-model="form.password" class="form-control" placeholder="Password">
                        </div>
                        <div class="form-group row mb-0">
                            <input class="btn btn-dark" type="submit" value="Login">
                        </div>
                        <div class="form-group row mb-0" v-if="authError">
                            <p class="error">
                                {{ authError }}
                            </p>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import {login} from '../helpers/auth';
    export default {
        name: "login",
        data() {
            return {
                form: {
                    email: '',
                    password: ''
                },
                error: null
            };
        },
        methods: {
            authenticate() {
                this.$store.dispatch('login');
                login(this.$data.form)
                    .then((res) => {
                        this.$store.commit("loginSuccess", res);
                        this.$router.push({path: '/'});
                    })
                    .catch((error) => {
                        this.$store.commit("loginFailed", {error});
                    });
            }
        },
        computed: {
            authError() {
                return this.$store.getters.authError;
            }
        }
    }
</script>

<style scoped>
    .error {
        text-align: center;
        color: red;
    }
</style>