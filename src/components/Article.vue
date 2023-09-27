<template>
    <div>
    <!-- to specify a type of prop 'string,number,boolean'array,or object -->

    <!-- props allow you transfer data from a parent component to the child component -->
    <h2 style="text-align:center">Article Component</h2>
    <h3>{{ title }}</h3>
    <h3>Likes ={{ likes }}</h3>
    <h3>Published= {{ IsPublished ? 'yes' :'No' }}</h3>
    </div>
</template>

<script>
    export default {
        // name:'Article', 
        //     props:{
        //     title:string,
        //        likes:number,
        //        IsPublished:Boolean,
        // },
       
    }
</script>

<style scoped>

</style>