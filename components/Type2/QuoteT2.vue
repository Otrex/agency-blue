<template>
  <main id="leads" class="d-container">
    <section class="">
      <div
        class="md:rounded-bl-[40px] md:rounded-bl-[40px] rounded-tl-[20px] rounded-tb-[20px] bg-[#3B57F4] grid md:grid-cols-2 items-start w-full"
      >
        <div
          class="lg:px-[50px] md:px-[24px] px-[16px] lg:py-[g0px] md:py-[24px] py-[20px]"
        >
          <h3
            class="lg:text-[60px] md:text-[40px] sm:text-[28px] text-[24px] text-[#fff] font-[700] md:leading-[65px]"
          >
            Get Free Consultation
          </h3>
          <p class="md:text-[18px] text-[16px] text-[#fff] mt-[16px]">
            Fill out your details Below to get a free Consultation.
          </p>
          <template v-if="!data?.agency_wizard.leads_collector"> 
            <form class="lg:mt-[50px] md:mt-[40px] mt-[24px] text-[#fff]">
              <input
                class="md:px-[24px] px-[12px] md:py-[20px] py-[16px] w-full border md:rounded-[100px] rounded-[50px] border-[#DCDCDC] bg-transparent lg:mb-[30px] md:mb-[24px] mb-[20px]"
                type="text"
                name="name"
                placeholder="Full Name"
              />
              <input
                class="md:px-[24px] px-[12px] md:py-[20px] py-[16px] w-full border md:rounded-[100px] rounded-[50px] border-[#DCDCDC] bg-transparent md:mb-[40px] mb-[25px]"
                type="email"
                name="email"
                placeholder="Email Address"
              />
              <button
                class="lg:w-[40%] md:w-[75%] bg-[#fff] md:py-[21px] py-[16px] md:px-[32px] px-[20px] md:text-[20px] text-[16px] text-[#3B57F4] rounded-[100px]"
              >
                Get Started
              </button>
            </form>
          </template>
          <template v-else>
            <div class="w-full pt-[1.5rem] force"> 
              <div class="w-full" v-html="data?.agency_wizard.leads_collector"></div>
            </div>
          </template>
        </div>
        <div class="flex items-center h-full">
          <img class=" rounded-tl-[2rem] rounded-bl-[2rem]" :src="data?.agency_wizard.leads_image || '/images/customer_agent.png'" alt="photo" />
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { WizardResponse } from "../../type";

defineProps<{ data?: WizardResponse }>();
</script>

<style>
.force * {
  @apply !text-white !bg-transparent;
}

.force h2 {
  @apply lg:!text-[60px] md:!text-[40px] sm:!text-[28px] !text-[24px] !text-[#fff] !font-[700] md:!leading-[65px];
}
.force input {
  @apply md:!px-[24px] !px-[12px] md:!py-[20px] !h-auto !py-[16px] !w-full !border md:!rounded-[100px];
  @apply !rounded-[50px] !border-[#DCDCDC] !bg-transparent lg:!mb-[30px] md:!mb-[24px] !mb-[20px];
}
.force input[type="submit"], .force button {
  @apply lg:!w-[40%] !flex !items-center !justify-center md:!w-[75%] !bg-[#fff] md:!py-[21px] !py-[16px] md:!px-[32px] !px-[20px];
  @apply md:!text-[20px] !text-[16px] !text-[#3B57F4] !rounded-[100px] !h-auto;
}
</style>
