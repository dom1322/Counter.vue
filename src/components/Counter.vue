<template>
  
    <h2>{{ CustomeTitle }}</h2>
    <p> {{  counter }}<sup>2</sup> = {{ SquareCounter }}</p>

    <div>
        <button v-on:click="increase">+1</button>
        <button v-on:click="decrease">-1</button>
    </div>

 
  
</template>

<script>
export default {
    props: {
        title: String,
        start: {
            type: Number,
            default: 100,
            validator(value) {
                return value < 100

            }
        }
    },

    data() {
        return {

            counter: this.start
        }
    },
    methods:{
        getSquareValue() {
            return this.counter * this.counter
        },

        increase() {
            this.counter += 1
        },
        decrease() {
            this.counter -= 1
        }

    },
    computed: {
        SquareCounter() {
            return this.counter * this.counter
        }
    },
        CustomeTitle() {
            return this.title || "Counter"
        }    
}
</script>


<style>

button{
    background-color: #64BB87;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;  
}

button:hover {
    background-color: #5aa67b;
    transition: 0.3 ease-in-out;
}


</style>
