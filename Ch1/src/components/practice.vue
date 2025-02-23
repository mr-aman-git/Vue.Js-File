<template>
    <div>
        <h1>Message: {{ isTrue ? 'yes' : 'no' }}</h1>
        <button v-on:click="myFunction">Submit</button>
    </div>
</template>

<script>
export default {
    name: 'practice',
    data() {
        return {
            isTrue: true, // Renamed variable
        };
    },
    methods: {
        myFunction() {
            console.log('click');
            this.isTrue = !this.isTrue; // Toggle between true and false
        }
    }
};
</script>
