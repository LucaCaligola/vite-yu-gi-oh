<template>
    <main>


        <h1>

        {{ store.searchText }}
        </h1>

    </main>
</template>

<script>

import { store } from '../../js/store';

export default {
    data() {
        return {
            store,
        }
    },
    
}


</script>

<style>

main{
    background-color: #D48F38;
    width: 100%;
    height: 500px
}
    
</style>