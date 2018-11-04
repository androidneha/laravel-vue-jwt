<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-9 mt-lg-5">
                <div class="card card-default">
                    <div class="card-header bg-dark text-white">Customers</div>
                    <div class="card-body">
                        <router-view></router-view>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'customers-main'
    }
</script>