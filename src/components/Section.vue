<script setup>
      const props = defineProps(['estado', 'calc'])

</script>

<template>
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
                        <input @keyup="evento => props.estado.campo1 = parseFloat(evento.target.value)" type="number" placeholder="0" value="0">
                        <select @change="evento => props.estado.calcSelect = evento.target.value" >
                            <option value="soma">+</option>
                            <option value="sub">-</option>
                            <option value="mult">*</option>
                            <option value="div">÷</option>
                        </select>
                        <input @keyup="evento => props.estado.campo2 = parseFloat(evento.target.value)" type="number" placeholder="0" value="0">
                    </form>
                    <span v-if="!isNaN(props.calc())" class="resultado"> {{ props.calc() }} </span>
                    <span v-else class="resultado"> Caractere inválido </span>


                </div>
            </div>
        </section>
</template>

<style scoped>
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
        color: rgb(19, 19, 19);
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
