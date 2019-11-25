<template>
    <p>Counter is: {{ counter }}</p>
</template>

<script>
    export default {
        computed:{
            counter(){
                // return this.$store.state.couter * 2;
                return this.$store.getters.doubleCounter;
            }
        }
        // props: ['counter']
    }
</script>