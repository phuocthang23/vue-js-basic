<script setup>
import { ref } from 'vue'

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
const count = ref(1)
const total = () => {
  count.value++
}

const object = ref({
  count: 2,
  user: {
    age: 18,
  },
  array: [1, 2, 3],
})

let n = 4

const Onchange = () => {
  object.value.count++
  object.value.user.age++
  object.value.array.push(n)
  n++
}

const OnReset = () => {
  object.value.count = 0
  object.value.user.age = 0
  object.value.array = [1, 2, 3]
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
  <button @click="total">click for total</button>
  <div>
    <p>Number: {{ count }}</p>
  </div>
  <div style="border: 2px solid #000; padding: 0 10px 10px 10px; width: 20%">
    <h2>Deep Reactivity</h2>
    <p>Increase: {{ object.count }}</p>
    <p>Age: {{ object.user.age }}</p>
    <p>Array: {{ object.array }}</p>
    <button @click="Onchange">increase</button>
    <span style="margin-left: 10px"><button @click="OnReset">Reset</button></span>
  </div>
</template>
