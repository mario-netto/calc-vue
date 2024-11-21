<script setup>
    import { reactive } from 'vue';
    import Header from './components/Header.vue';
    import Section from './components/Section.vue';

    const estado = reactive({
        calcSelect: 'soma',
        campo1: 0,
        campo2: 0,
        resultado: 0,
    });

    function calc() {
        switch (estado.calcSelect) {
            case 'soma':
                return estado.campo1 + estado.campo2;
            case 'sub':
                return estado.campo1 - estado.campo2;
            case 'mult':
                return estado.campo1 * estado.campo2;
            case 'div': 
                return estado.campo1 / estado.campo2;
        }
    }
</script>

<template>
    <body>
        <Header />
        <Section :estado="estado" :calc="calc"/>
    </body>
</template>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}

body {
    background-color: #F5CB47;
    height: 100vh;
}

.container {
    max-width: 1024px;
    margin: 0 auto;
}
</style>
