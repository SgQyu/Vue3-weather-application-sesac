<template>
  <div>
    <ul class="city-selector">
      <li
        @click="selectCity(city)"
        :class="{ isSelected: city.selected === true }"
        v-for="city in cities"
        :key="city.code"
      >
        {{ city.label }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CitySelector",
  data() {
    return {
      cities: [
        { code: "Seoul", label: "서울", selected: false },
        { code: "Tokyo", label: "도쿄", selected: false },
        { code: "London", label: "런던", selected: false },
        { code: "Moscow", label: "모스크바", selected: false },
        { code: "Yakutsk", label: "야크추크", selected: false },
      ],
    };
  },
  methods: {
    selectCity(city) {
      city.selected = !city.selected;
      this.$emit("selectCity", city);
    },
  },
};
</script>

<style lang="scss" scoped>
@mixin center {
  display: flex;
  justify-content: center;
  align-items: center;
  @content;
}

.city-selector {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  li {
    @include center;
    border: 0.05em solid #efefef;
    padding: 0.3em;
    cursor: pointer;
    &.isSelected {
      background-color: #fd1d1d;
      color: #fff;
    }
  }
}
</style>
