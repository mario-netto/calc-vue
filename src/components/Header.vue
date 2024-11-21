<script setup>
</script>

<template>
    <header>
        <div class="header container">
            <img class="img-calcae" src="../assets/calcae.png" alt="">
            <img class="img-calc" src="../assets/calc.png" alt="">
        </div>
    </header>
</template>

<style scoped>
    .header {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #F196E5;
    padding: 16px 0;
    }

    .img-calcae {
        display: inline-block;
        max-width: 500px;
    }

    .img-calc {
        display: inline-block;
        max-width: 300px;
        margin-right: 26px;
        margin-top: 16px;
    }

    @media (max-width: 1023px) {
        .img-calcae {
        max-width: 50%;
    }

        .img-calc {
            max-width: 30%;
            margin-right: 26px;
            margin-top: 16px;
        }
    }
</style>