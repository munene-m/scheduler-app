<script lang="ts" setup>
import CustomButton from '../components/CustomButton.vue'
import ConfirmedBooking from '../components/ConfirmedBooking.vue'
</script>

<template>
  <main>
    <section
      class="pt-14 mx-6 md:mx-20 lg:mx-28 pb-10 flex items-center justify-between gap-8 flex-wrap md:flex-nowrap"
    >
      <div class="w-fit">
        <h1 class="text-5xl font-extrabold md:w-1/2 pb-5">
          Online Booking Made Simple, Your Appointments
          <span
            class="bg-clip-text text-transparent bg-gradient-to-r from-gradientTwo to-gradientOne"
            >Sorted.</span
          >
        </h1>
        <p class="md:w-96">
          With our intuitive online booking system, scheduling appointments has never been easier.
        </p>

        <div class="mt-7">
          <span class="text-slate-500 text-sm text-center">Sign up for free with Google</span>
          <div class="flex items-center gap-4 mt-2">
            <CustomButton
              class="bg-primary text-white w-fit py-2 px-3 rounded cursor-pointer flex items-center gap-2"
            >
              Get started
            </CustomButton>
            <CustomButton
              class="border border-primary text-primary w-fit py-2 px-3 cursor-pointer rounded flex items-center gap-2"
            >
              Learn more
            </CustomButton>
          </div>
        </div>
      </div>
      <ConfirmedBooking />
    </section>
  </main>
</template>
