<template>
  <div class="loader">
    <img src="../assets/img/Disk_animation.svg" alt="immagine di caricamento" />
    <div class="text">Loading...</div>
  </div>
</template>

<script>
export default {
  name: 'MyLoader',
};
</script>

<style lang="scss" scoped>
.loader {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  img {
    width: 100px;
  }
}
.text {
  text-align: center;
  font-size: 1.5rem;
  padding-top: 5px;
  color: #1ed760;
}
</style>
>
