<template>
    <div class="card">
        <slot> </slot>
    </div>
</template>

<script>
    export default {
        name:'card',
    }
</script>

<style scoped>

.card{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
    padding: 16px;
    margin-bottom: 20px;
    width: 200px;
}
.card:hover{
    box-shadow:0 8px 16px rgba(0, 0, 0, 0.2)
}
</style>