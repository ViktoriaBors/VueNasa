<template>
<div class="flex justify-center mt-11">
 <div
    class="
      block
      p-6
      rounded-lg
      shadow-lg
      bg-white
      md:w-96
      opacity-90
      border-2 border-sky-900
    "
  >
    <form>
      <div class="form-group mb-6">
        <div class="flex items-center justify-center">
        <div class="datepicker relative form-floating mb-3 xl:w-96" data-mdb-toggle-button="false">
            <input type="text"
            class="form-control block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-300 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
            placeholder="Select a date" data-mdb-toggle="datepicker" />
            <label for="floatingInput" class="text-gray-700">Select a date</label>
    </div>
    </div>
      </div>
      <div class="form-group mb-6">
        <input type="date" name="date" id="date" :max="dateComputed">
        <label for="date">Select a date</label>
      </div>
      <button
        type="submit"
        @click.prevent="query"
        class="
          w-full
          px-6
          py-2.5
          bg-sky-600
          text-white
          font-medium
          text-xs
          leading-tight
          uppercase
          rounded
          shadow-md
          hover:bg-sky-700 hover:shadow-lg
          focus:bg-sky-700 focus:shadow-lg focus:outline-none focus:ring-0
          active:bg-sky-800 active:shadow-lg
          transition
          duration-150
          ease-in-out
        "
      >
        Submit
      </button>
    </form>
  </div>
</div>
 
</template>

<script>
    
export default {
    data(){
        return{
            today: (new Date(Date.now())).toISOString(),
        }
    },
    computed:{
        dateComputed(){
            return this.today.slice(0,10)
        }
   
    }
};
</script>

<style>
</style>