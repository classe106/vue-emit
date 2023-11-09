<script>
import ComponenteA from './components/ComponenteA.vue';
import ComponenteB from './components/ComponenteB.vue';

import { store } from './store';

import axios from 'axios';
export default {
    components: {
        ComponenteA,
        ComponenteB
    },
    data() {
        return {
            message: "CIAO",
            store: store,
        }
    },
    methods: {
        decrease(value) {
            // this.store.counter -= value;
            console.log('decrease', value);
        },
        decreaseComplex(obj) {
            // this.store.counter -= obj.value;
            // console.log(obj.status);
            console.log('decreaseComplex', obj);
        }
    }
}
</script>

<template>
    <h2>{{ message }}</h2>
    <ComponenteA />
    <ComponenteB @decrease-counter="decrease" @decrease-counter-complex="decreaseComplex" />
</template>

<style scoped>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
}

.logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
    filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
