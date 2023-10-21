<template>
    <div v-editable="blok">
        <img
            :src="blok.image.filename"
            :alt="blok.image.alt"
        >

        <div class="container">
            <h1>{{ blok.title }}</h1>
            <h2>{{ blok.description }}</h2>
            <div v-html="resolvedRichText"></div>

            <div>Written by: {{ blok.author }}</div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({ blok: Object })

const resolvedRichText = computed(() => renderRichText(props.blok.content))
</script>