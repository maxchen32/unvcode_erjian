<script lang="ts" setup>
import { computed, ref } from 'vue';
import d from './d.json'

const input = ref('')
const output = computed(() => {
  let s = ''
  for (const c of input.value) {
      if (d[c])
          s += `<span style="color:blue">${d[c]}</span>`
      else
          s += c
  }
  return s
})
</script>

<template>
  <h1>
    二简code
  </h1>
  <p>
    <input class="synth" type='text' placeholder='输入你的字' v-model="input" />
  </p>
  <p>
    转换结果
  </p>
  <p class="怪">
    <span v-html='output'></span>
  </p>
  <div class="底">
    <p>
      © 2023 | Rimo | maxchen32 | MPL-2.0
    </p>
  </div>
</template>
