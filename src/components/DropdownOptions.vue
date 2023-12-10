<template>
  <div
    class="box type-btn d-flex justify-content-between align-items-center pe-3 ps-3"
    @click="show = !show"
  >
    <p class="m-0 d-flex align-items-center">{{ typeSelected }}</p>
    <img class="img-fluid" :src="arrowDown" />
  </div>
  <div class="dropdown-content mt-1" v-show="show">
    <div
      class="dropdown-item pb-3"
      v-for="(dropdownOption, index) in options"
      :key="index"
      :class="{ active: typeSelected === options[index] }"
    >
      <button
        class="btn mt-2 ps-0 type-option text-start"
        @click="onOptionClick(dropdownOption)"
      >
        {{ dropdownOption }}
      </button>
    </div>
  </div>
</template>
<script>
import arrowDown from "/src/assets/images/arrow-down.svg";

export default {
  props: {
    options: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      arrowDown: arrowDown,
      show: false,
      typeSelected: this.options[0],
    };
  },
  methods: {
    showDropdown() {
      this.show = !this.show;
    },
    onOptionClick(option) {
      this.typeSelected = option;
      this.show = false; // Hide the dropdown after selecting an option
      this.$emit('update:typeSelected', option); // Emit the updated value to the parent
    },
  },
};
</script>
<style scoped>
.type-btn {
  cursor: pointer;
}

.dropdown-content {
  position: absolute; /* to make appears above other elements on the page. */
  width: 100%;
  max-width: 500px;
  height: fit-content;
  border-radius: 10px;
  background: var(--middle-blue-color);
  text-indent: 20px;
}

.dropdown-item {
  color: var(--white-color);
}
.dropdown-item:hover {
  background-color: var(--second-blue-color);
}
.dropdown-item:first-child {
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

.dropdown-item:last-child {
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
.type-option {
  color: var(--white-color);
  border: none;
  outline: none;
  width: 100%;
}

.active {
  background-color: var(--second-blue-color);
}

.box {
  width: 100%;
  max-width: 500px;
  height: 60px;
  border-radius: 10px;
  background: var(--middle-blue-color);
  color: var(--white-color);
}
</style>
