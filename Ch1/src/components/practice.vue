<template>
    <div>
        <table>
            <tr class="border">
                <td class="border p-4 font-bold">Name</td>
                <td class="border p-4 font-bold">messsage</td>
                <td class="border p-4 font-bold">Response</td>
            </tr>

            <tr class="border" v-for="user in users">
                <td class="border p-4">{{user.name}}</td>
                <td class="border p-4">{{user.message}}</td>
                <td class="border p-4">{{user.response ? 'yes':'no'}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
export default{
    name: 'practice',
    data(){
        return{
            users:[
                {name:'Aman', message:'Hello', response:true},
                {name:'Vishal', message:'Hey', response:true},
                {name:'Sachin', message:'Good Morning', response:false},
            ]
        }
    }
}

</script>