<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Vuex</h1>
                <app-result></app-result>
                <hr>
                <app-anoter-result></app-anoter-result>
                <hr>
                <app-counter></app-counter>
                <app-anoter-counter></app-anoter-counter>
                <hr>
                <input type="text" :value="value" @input="updateValue">
                <input type="text" v-model="value">
                <p>{{ value }}</p>
            </div>
        </div>
    </div>
</template>

<script>
    import Counter from './components/Counter.vue';
    import Result from './components/Result.vue';
    import AnoterResult from './components/AnoterResult.vue';
    import AnoterCounter from './components/AnoterCounter.vue';

    export default {
        computed:{
            value: {
                get(){
                    return this.$store.getters.value;
                },
                set(value){
                    this.$store.dispatch('updateValue', value);
                }
            }
        },
        methods: {
            updateValue(event){
                this.$store.dispatch('updateValue', event.target.value);
            }
        },
        // data() {
        //     return {
        //         counter: 0
        //     }
        // },
        components: {
            appCounter: Counter,
            appResult: Result,
            appAnoterResult: AnoterResult,
            appAnoterCounter: AnoterCounter
        }
    }
</script>

