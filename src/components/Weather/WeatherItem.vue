<template>
  <li class="weather-item">
    <h3>{{ weather.label }}</h3>
    <p class="temperature">{{ weather.temperature }} C&deg;</p>
    <p class="info">
      <img :src="weather.icon" alt="image" />
      <span>습도 : {{ weather.humidity }}</span>
      <span>바람 : {{ weather.wind }}m/s</span>
    </p>
  </li>
</template>

<script>
export default {
  name: "WeatherItem",
  props: {
    weather: {
      type: Object,
      default() {
        return {
          label: "서울",
          code: "Seoul",
          temperature: 20,
          humidity: 15,
          wind: 1.5,
        };
      },
    },
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
.weather-item {
  @include center;
  flex-direction: column;
  border: 1px solid #efefef;
  padding: 0.5em;
  h3 {
    font-size: 14px;
    color: #333;
  }
  .temperature {
    font-size: 36px;
  }
  .info {
    @include center;
    font-size: 12px;
    * {
      margin-right: 0.4em;
    }
  }
}
</style>
