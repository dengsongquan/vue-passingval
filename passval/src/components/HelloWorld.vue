<template>
    <ul>
        <li v-for="todo in todos" :key="todo.id">
            <slot :todo="todo">

            </slot>
        </li>
    </ul>
    <input type="text" :value="msg" @input="$emit('input',$event.target.value)">
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg:'',
            todos:{
                type: Array
            }
        },
        data(){
            return{
                sonValue: this.fatherValue
            }
        },
        watch:{
            sonValue(newValue, oldValue){
                this.$emit('update:fatherValue', newValue);
            },
            fatherValue(newValue){
                this.sonValue = newValue;
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
