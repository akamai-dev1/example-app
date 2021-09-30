<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        <b-button
                            @click="clicked">
                            Request from Api
                        </b-button>
                        <br />
                        Response: 
                        {{sample}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                "sample": {}
            };
        },
        mounted() {
            console.log('Component mounted.');
        },
        methods: {
            clicked () {
                var self = this;
                axios.get('/api/sample').then(function (response) {
                    var data = response.data;
                    
                    self.sample = data.data.concat(['this is a sample api response you can play with']);
                });
            }
        }
    }
</script>
