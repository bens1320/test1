<template>
    <div class="red warpper" >
        <input type="text" :value="value" @input="$emit('input', $event.target.value)
        ">
    </div>
</template>
<script>
    export default {
        name: "MyInput",
        props:{
            value:{
                type: String
            }
        }
    }
</script>

<style scoped>
    .red{
        background: red;
    }

    .warpper{
        display: inline-block;
    }
</style>