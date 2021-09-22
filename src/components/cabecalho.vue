<template>
  <header>
      <h1> {{valor}} </h1>
  </header>
</template>

<script>
export default {
   props: ["valor"]
};
</script>

<style>
header {
    top: 0;
    display: flex;
    margin-left: 0px;
    height: 50px;
    width: 100%;
    color: #fff;
    position: fixed;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle, #0000FF 0, #191970 100%);
}
</style>