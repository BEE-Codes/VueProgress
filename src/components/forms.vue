<template>
    <div>
        <form action="" method="">
            <p> {{ message }}</p>
            <textarea v-model="message" placeholder="write whatever you want here" cols="30" rows="10"></textarea>

            <!-- checkBox -->
            <input type="checkbox" id="checkbox" v-model="checked" />
            <label for="checkbox">{{ checked }}</label>
            

            <!-- using multiple check boxes -->
            <div> Checked names: {{ checkedNames }}</div>

            <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
            <label for="jack">Jack</label>
            
            <input type="checkbox" id="john" value="John" v-model="checkedNames" />
            <label for="john">John</label>
            
            <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
            <label for="mike">Mike</label>

            <!-- radio -->
            <div>Picked: {{ picked }}</div>

            <input type="radio" id="one" value="One" v-model="picked" />
            <label for="one">One</label>

            <input type="radio" id="two" value="Two" v-model="picked" />
            <label for="two">Two</label>

            <!-- select -->
            <div>Selected: {{ selected }}</div>

            <select v-model="selected">
            <option disabled value="">Please select one</option>
            <option>A</option>
            <option>B</option>
            <option>C</option>
            </select>

        </form>
        <!-- emit -->
        <button @click="$emit('helloWorld')">Click me</button>
    </div>
</template>

<script>
export default{
    data (){
        return {
            message:'',
            checked:true,
            checkedNames:[],
            picked:'',
            selected:'',
        }
    },
    method:{
        submit(){
            this.$emit('helloWorld')
        }

    }
}

</script>