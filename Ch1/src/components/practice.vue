<template>
    <table class="border m-auto">
        <tr class="border">
            <td class="border font-bold p-4">Id</td>
            <td class="border font-bold p-4">Name</td>
            <td class="border font-bold p-4">No</td>
            <td class="border font-bold p-4">Action</td>
        </tr>
        <tr v-for="(user, index) in users" :key="user.id" class="border">
            <td class="border p-4">{{ user.id }}</td>
            <td class="border p-4">
                <span v-if="!user.isEditing">{{ user.name }}</span>
                <input v-else v-model="user.name" class="border p-1" />
            </td>
            <td class="border p-4">
                <span v-if="!user.isEditing">{{ user.no }}</span>
                <input v-else v-model="user.no" class="border p-1" />
            </td>
            <td class="border p-4">
                <button v-if="!user.isEditing" class="bg-green-500 text-white p-2 rounded mr-2" @click="editUser(index)">Edit</button>
                <button v-else class="bg-blue-500 text-white p-2 rounded mr-2" @click="saveUser(index)">Save</button>
                <button class="bg-red-500 text-white p-2 rounded" @click="deleteUser(index)">Delete</button>
            </td>
        </tr>
    </table>
</template>

<script>
export default {
    name: "practice",
    data() {
        return {
            users: [
                { id: '1', name: 'Aman', no: '12279', isEditing: false },
                { id: '2', name: 'Sachin', no: '12280', isEditing: false },
                { id: '3', name: 'Rahul', no: '12281', isEditing: false },
                { id: '4', name: 'Vikas', no: '12282', isEditing: false },
                { id: '5', name: 'Neha', no: '12283', isEditing: false },
            ]
        };
    },
    methods: {
        deleteUser(index) {
            this.users.splice(index, 1);
        },
        editUser(index) {
            this.users[index].isEditing = true;
        },
        saveUser(index) {
            this.users[index].isEditing = false;
        }
    }
};
</script>
