<script setup>
    import { reactive } from 'vue';

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
        <!-- header  -->
        <header>
            <div class="container">
                <img class="img-calcae" src="./assets/calcae.png" alt="">
                <img class="img-calc" src="./assets/calc.png" alt="">
            </div>
        </header>
        <!-- área de input e calc -->
        <section>
            <div class="custom-shape">
                <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120"
                    preserveAspectRatio="none">
                    <path d="M892.25 114.72L0 0 0 120 1200 120 1200 0 892.25 114.72z" class="shape-fill"></path>
                </svg>
            </div>
            <div class="section container">
                <div class="form-content">
                    <form>
                        <input @keyup="evento => estado.campo1 = parseFloat(evento.target.value)" type="number" placeholder="0" value="0">
                        <select @change="evento => estado.calcSelect = evento.target.value" >
                            <option value="soma">+</option>
                            <option value="sub">-</option>
                            <option value="mult">*</option>
                            <option value="div">÷</option>
                        </select>
                        <input @keyup="evento => estado.campo2 = parseFloat(evento.target.value)" type="number" placeholder="0" value="0">
                    </form>
                    <span class="resultado"> {{ calc() }} </span>
                </div>
            </div>
        </section>
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

header {
    display: flex;
    justify-content: center;
    background-color: #F196E5;
    padding: 16px 0;
}

.img-calcae {
    max-width: 500px;
}

.img-calc {
    max-width: 300px;
    margin-right: 26px;
    margin-top: 16px;
}

section {
    position: relative;
    background-color: #F5CB47;
    /* height: 59vh; */
}

.section {
    padding-top: 64px;
}

.form-content {
    text-align: center;
}

.resultado {
    display: block;
    font-size: 3em;
    font-weight: bold;
    margin-top: 24px;
    padding-bottom: 24px;
}

.text-content {
    margin-top: 60px;
}

.text-content h1 {
    margin-bottom: 8px;
}

input,
select {
    width: 64px;
    height: 40px;
    border-radius: 8px;
    border: none;
}

select {
    margin: 0 32px;
}

.custom-shape {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
    transform: rotate(180deg);
}

.custom-shape svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 32px;
}

.custom-shape .shape-fill {
    fill: #F196E5;
}
</style>
