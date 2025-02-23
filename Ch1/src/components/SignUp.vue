<template>
  <div class="flex justify-center w-[100%] h-[100vh] bg-gray-100">
    <div class="w-[400px] h-[500px] mt-5 rounded-md bg-white shadow-2xl ">
        <div class="ml-34">
            <img src="../assets/resto-logo.png" alt="" class="w-[100px]" />

            <h1 class="text-[30px] font-bold text-[#613912]">Sign Up</h1>
        </div>
        <div class="flex flex-col justify-center ml-13 mt-10 gap-5">
            <input type="text" v-model="name" placeholder="Enter Name" class="w-[270px] h-10 border border-[#613912] outline-none pl-2 rounded-md"/>
            <input type="email" v-model="email" placeholder="Enter Email" class="w-[270px] h-10 border border-[#613912] outline-none pl-2 rounded-md"/>
            <input type="password" v-model="password" placeholder="Enter Password" class="w-[270px] h-10 border border-[#613912] outline-none pl-2 rounded-md"/>
            
        </div>
        <button class="w-[150px] h-12 bg-blue-500 rounded-md ml-28 mt-7 cursor-pointer" v-on:click="signup">Register</button>
    </div>
  </div>
</template>




<script>
import axios from 'axios';
export default {
  name: "SignUp",
  data()
  {
    return{
        name: '',
        email: '',
        password: ''
    }
  },
  methods: {
    async signup(){
        
        let result= await axios.post ("http://localhost:3000/user",{
            name: this.name,
            email: this.email,
            password: this.password
        })
        if(result.status==201){
            alert("sucessfull");
        }else{
            alert('Failed');
        }
        localStorage.setItem("user-info", JSON.stringify(result.data));
    }

  }
};
</script>
