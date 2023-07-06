<template>
  <HeaderDisplay />
  <WeatherContent />
</template>

<script>
import HeaderDisplay from "./components/Layouts/HeaderDisplay";
import WeatherContent from "./components/Weather/WeatherContent";

export default {
  components: {
    HeaderDisplay,
    WeatherContent,
  },
};
</script>

<style lang="scss" scoped></style>
