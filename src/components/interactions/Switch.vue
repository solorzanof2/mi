<template>
  <MaterialSwitch>
    <input type="checkbox" />
    <Slider class="slider" />
  </MaterialSwitch>
</template>

<script>
import styled from "vue-styled-components";

const MaterialSwitch = styled.label`
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;

  & > input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  & > input:checked + .slider {
    background-color: #068cfa;
  }

  & > input:checked + .slider::before {
    transform: translateX(26px);
  }
`;

const Slider = styled.span`
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  transition: background-color 0.4s;

  &::before {
    position: absolute;
    content: "";
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    transition: transform 0.4s;
  }
`;

export default {
  components: {
    MaterialSwitch,
    Slider
  }
};
</script>
