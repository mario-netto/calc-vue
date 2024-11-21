<script setup>
</script>

<template>
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
      <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
          <path d="M892.25 114.72L0 0 0 120 1200 120 1200 0 892.25 114.72z" class="shape-fill"></path>
      </svg>
  </div>
    <div class="section">
      
    </div>
  </section>
</template>

<style scoped>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
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
    height: 100vh;
  }

  .custom-shape{
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
    height: 127px;
    transform: rotateY(180deg);
}

.custom-shape .shape-fill {
    fill: #F196E5;
}
</style>
