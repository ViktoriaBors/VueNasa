<template>
  <div class="w-screen h-screen flex justify-center items-center">
    <div
      v-if="!isDataArrived"
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
          <p class="pb-4">Select a date</p>
          <input
            v-model="dateChosen"
            class="
              block
              w-full
              px-3
              py-1.5
              text-base
              font-normal
              text-gray-700
              bg-white bg-clip-padding
              border border-solid border-gray-300
              rounded
              transition
              ease-in-out
              m-0
              focus:text-gray-700
              focus:bg-white
              focus:border-blue-600
              focus:outline-none
            "
            type="date"
            name="date"
            id="date"
            :max="dateComputed"
          />
        </div>
        <p class="text-sm pb-2 text-orange-800" v-if="!dateChosen">
          You must choose a date
        </p>
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
    <div v-if="isDataArrived">
      <div class="flex justify-center">
        <div class="rounded-lg shadow-lg bg-white max-w-2xl">
            <img
              class="rounded-t-lg"
              :src="imgUrl"
              :alt="imgDesc"
            />
          <div class="p-6">
            <h5 class="text-gray-900 text-xl font-medium mb-2">{{imgTitle}} </h5>
            <p class="text-sm text-gray-700 text-base mb-4">
              {{imgDesc}}
            </p>
            <button
            @click="isDataArrived = false"
              type="button"
              class="
                inline-block
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
                focus:bg-sky-700
                focus:shadow-lg
                focus:outline-none
                focus:ring-0
                active:bg-sky-800 active:shadow-lg
                transition
                duration-150
                ease-in-out
              "
            >
              See another one
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      today: new Date(Date.now()).toISOString(),
      isDataArrived: false,
      dateChosen: "",
      imgUrl: "",
      imgDesc: "",
      imgTitle: ""

    };
  },
  computed: {
    dateComputed() {
      return this.today.slice(0, 10);
    },
  },
  methods: {
    query() {
      console.log("get img");
      console.log(this.dateChosen);
      if (!this.dateChosen) {
        return;
      }
      let url =
        "https://api.nasa.gov/planetary/apod?date=" +
        this.dateChosen +
        "&api_key=DEMO_KEY";
      fetch(url)
        .then((res) => res.json())
        .then((data) => {
          this.isDataArrived = true;
          console.log(data);
          this.imgUrl = data.url;
          this.imgDesc = data.explanation
          this.imgTitle = data.title
        });
    },
  },
};
</script>

<style>
</style>