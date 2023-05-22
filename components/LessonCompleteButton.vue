<template>






<label>
<input
type="checkbox"
:value="modelValue"
@input="() => $emit('update:modelValue',!modelValue)"
class="hidden"
/>
{{modelValue ? 'Completed!': 'Mark as complete'}}
</label>
</template>

<script setup>
defineProps({
    modalValue:{
        type: Boolean,
        default: false,

    },
});
defineEmits(['update:modelValue']);
</script>
<style scoped>
::selection{
    display: none;
}
</style>