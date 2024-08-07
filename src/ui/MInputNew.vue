<script setup lang="ts">
interface Props {
  type?: string
  severity?: string
}

const value1 = defineModel({ default: '' })
const value2 = defineModel({ default: '' })
const value3 = defineModel({ default: '' })

withDefaults(defineProps<Props>(), { type: 'text', severity: 'info' });
</script>

<template>
  <div class="card flex flex-col items-center gap-4">
    <InputText v-model="value1" :type="type" size="small" placeholder="Small" />
    <InputText v-model="value2" :type="type" placeholder="Normal" />
    <InputText v-model="value3" :type="type" size="large" placeholder="Large" />
    <slot name="icon" />
    <slot name="body" />
  </div>
</template>
