<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <button v-myOn="crazyCounter">
                    Don't Press the Button!
                </button>
                <hr>
                <h3>
                    {{counter}}
                </h3>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                counter: 0
            }
        },
        directives: {
            myOn : {
                bind(el, binding){
                    el.onclick = function() {
                        binding.value();
                    }
                }
            }
        },
        methods: {
            crazyCounter(){
                setInterval(() => {
                    this.counter ++
                }, 1)
                
            }
        }
    }
</script>

<style>
</style>
