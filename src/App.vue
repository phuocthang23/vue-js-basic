<script setup>
const message = 'hello anh em'
const rawHtml = '<span style="color: red">This should be red.</span>'
const buttonId = 'button-1'
const buttonClass = 'btn btn-primary'
const isButtonDisabled = true
const ojectOffset = {
  id: 'oject-offset',
  class: 'btn btn-primary',
  style: {
    color: 'blue',
    fontSize: '20px',
  },
}
</script>

<template>
  <h1>Syntax</h1>
  <span>Message: {{ message }}</span>
  <p>Using text interpolation: {{ rawHtml }}</p>
  <p>Using v-html directive: <span v-html="rawHtml"></span></p>
  <!-- HTML will be rendered with style-->
  <button :id="buttonId" :class="buttonClass">Click</button>
  <button :disabled="isButtonDisabled">Button</button>
  <button v-bind="ojectOffset">click here</button>
</template>
