<template>
    <ol>
        <li v-for="Units in unitsList" :key="Units">
        {{ Units.type }}/{{ Units.rate }}
        </li>
    </ol>
</template>
<script>
export default {
  props: ['unitsList'],
};
</script>