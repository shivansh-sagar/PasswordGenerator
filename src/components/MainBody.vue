<template>
  <div class="flex flex-col pt-20 bg-slate-200 h-screen items-center">
    <h1 class="text-center font-mono font-bold text-2xl">PASSWORD GENERATOR</h1>
    <div class="w-100 flex flex-col items-center justify-center w-3/4 h-1/3">
      <form
        class="flex border-2 rounded-md px-2 justify-evenly flex-col align-middle w-80 h-48"
        @submit.prevent="generate()"
      >
        <input
          class="p-2 m-2 border-b-2 bg-slate-200 border-blue-300 focus:outline-none focus:border-t-2 focus:border-blue-400 focus:shadow-md focus:shadow-blue-200 focus:placeholder-slate-400"
          required
          type="number"
          placeholder="Enter Password length"
          v-model="userInput"
        /><button
          class="bg-blue-400 hover:bg-blue-500 h-16 rounded-md"
          type="submit"
        >
          Generate
        </button>
      </form>
    </div>
    <p>Your Password appers here:</p>
    <div class="bg-slate-500 passDiv text-white font-mono rounded-md">{{ pwd }}</div>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      userInput: "",
      pwd: "",
      arr: "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890~!@#$%^&*_",
      error: "",
    };
  },
  methods: {
    generate() {
      if (this.userInput > 60) {
        window.alert("Password length should be less than 20");
        this.userInput="";
      }
      this.pwd = "";
      for (let i = 1; i <= this.userInput; i++) {
        let a = Math.floor(Math.random() * this.arr.length);
        this.pwd += this.arr[a];
        this.error = "";
      }
    },
  },
};
</script>

<style>
.span {
  background-color: rgb(4, 136, 136);
  color: white;
  font-weight: 700;
}
.passDiv{
  width: 80%;
  text-align: center;
}
@media screen and (min-width: 900px) {
  .passDiv{
    width: 40%;
  }
}
  

div.passDiv{
  word-wrap:break-word ;
}

/*  */
</style>
