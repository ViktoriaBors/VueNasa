<template>
  <div>
    <div class="p-14">
      <div>
        <h2 class="font-semibold text-5xl uppercase mb-4">Nasa Images</h2>
        <h4 class="font-semibold text-xl m-11">
          Pick a date and see "Picture of the day" from Nasa
        </h4>
        <router-link          
            class="
            text-gray-800
            font-medium
            text-sm
            font-bold
            leading-snug
            uppercase
          "
            :to="{ name: 'form' }"
      
        >Start here</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: {},
};
</script>

<style>
</style>
