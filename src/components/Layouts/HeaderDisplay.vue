<template>
  <header id="header">
    <h2>Weather Application</h2>
    <p>{{ username }}님 반갑습니다.</p>
  </header>
</template>

<script>
export default {
  name: "HeaderDisplay",
  data() {
    return {
      username: "",
    };
  },
};
</script>

<style scoped lang="scss">
@mixin center {
  display: flex;
  justify-content: center;
  align-items: center;
  @content;
}

#header {
  background: linear-gradient(15deg, #00b4db, #0083b0, #005aa7, #fffde4);
  padding: 1em;

  @include center {
    justify-content: space-between;
  }

  h2 {
    color: #fff;
  }

  p {
    font-size: 12px;
    color: #fff;
  }
}
</style>
