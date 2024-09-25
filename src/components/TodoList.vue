<template>
    <FwbListGroupItem class="flex justify-between items-center">
        <span>{{ props.index + 1 }}.
            {{ props.todo }}</span>

        <!-- button: remove todo -->
        <FwbButton @click="emits('remove-todo', index)" size="sm" color="red">
            <TrashIcon class="w-3" />
        </FwbButton>
    </FwbListGroupItem>
</template>

<script setup>

import { FwbButton, FwbListGroupItem } from 'flowbite-vue';
import { TrashIcon } from "@heroicons/vue/24/outline"

// props
const props = defineProps({
    todo: String,
    index: Number
})

// emits
const emits = defineEmits(["remove-todo", "transfer-data"])

</script>