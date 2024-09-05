<template>
    <button @click="$emit('OnClick')">
        <slot/>
    </button>
</template>