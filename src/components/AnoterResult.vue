<template>
    <div>
        <p>Counter is: {{ doubleCounter }}</p>
        <p>Number Of Clickl: {{ stringCounter }}</p>
    </div>
    
</template>

<script>
    import { mapGetters } from 'vuex';
    import * as types from '../store/types';
    export default {
        // computed:{
        //     counter(){
        //         return this.$store.getters.doubleCounter;
        //     },
        //     clicks(){
        //         return this.$store.getters.stringCounter;
        //     }
        // }
        computed: {
            ...mapGetters({
                doubleCounter: types.DOUBLE_COUNTER,
                stringCounter: types.CLICK_COUNTER
            })
        }
        
    }
</script>