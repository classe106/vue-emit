<script>
import { store } from '../store.js'

export default {
    emits: ['decreaseCounter', 'decreaseCounterComplex'],
    data() {
        return {
            store: store,

        }
    },
    methods: {
        add() {
            // Modifico il valore di una proprietà dello store
            this.store.counter++;
        },
        complexEmit() {
            if (this.store.counter > 0) {
                const obj = { value: 1, status: 'success' };
                this.$emit('decreaseCounterComplex', obj)
            }
        }
    }
}
</script>

<template>
    <div class="buttons-container">
        <!-- Chiamo un metodo del componente -->
        <button @click="add()">Counter++ COMPONENTE</button>

        <!-- Chiamo un metodo dello store -->
        <button @click="store.storeAdd()">Counter++ STORE</button>

        <button @click="$emit('decreaseCounter', 1)">Decrease Counter EMIT</button>

        <button @click="complexEmit()">Decrease Counter Complex EMIT</button>
    </div>
</template>

<style>
.buttons-container {
    display: flex;
    flex-direction: column;
}

.buttons-container button {
    margin: 10px 0;
}
</style>