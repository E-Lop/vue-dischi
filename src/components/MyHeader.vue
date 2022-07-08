<template>
  <div class="header_content">
    <div class="logo">
      <img
        src="../assets/img/Spotify_logo_without_text.svg.png"
        alt="Logo Spotify"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyHeader',
};
</script>

<style lang="scss" scoped>
@import '../style/variables';

.header_content {
  background-color: $main_color;
  padding: 10px 20px;
}

.logo {
  width: 30px;
}
</style>
