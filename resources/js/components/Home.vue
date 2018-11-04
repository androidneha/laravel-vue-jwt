<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-12 mt-5">
                <div class="card card-default">
                    <div class="card-header bg-dark text-white text-center">{{ welcome }}</div>
                    <div class="card-body">
                        <img class="img-fluid" src="https://cdn-images-1.medium.com/max/2000/1*OGCE-B4onkKZyAzf1Ge0Ew.png" alt="WeCode">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Home",
        computed: {
            welcome() {
                return this.$store.state.welcome
            }
        }
    }
</script>

<style scoped>

</style>