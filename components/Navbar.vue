<template>
  <nav class="navbar navbar-expand-lg bgg">
    <div class="container">
      <h1 class="pp"><strong>Apotek Xyz</strong></h1>
      <slot></slot>
    </div>
  </nav>
</template>


<style scoped>
.bgg {
  background-color: #83A0C3;
  height: 100px;
}

.pp {
  font-size: 1.7em;
}

</style>
