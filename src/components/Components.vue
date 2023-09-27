<template>
    <div>
        <!-- components make up the entire ui of a web application and they are reusable-->
        <!-- registering components may be done either globally or locally -->

        <h3> Hello {{ name }} i am a {{ thing }} </h3>
<!-- 
        <p>Non Prop attributes are attributes passed into a component but does not have a property defined in props
            examples include; class,id,and style attribute
        </p> -->

        <!-- Api in vue "inject","project" -->
        

    </div>
</template>

<script>
    export default {
    
        props:['name','thing']
    }
</script>

<style scoped>

</style>