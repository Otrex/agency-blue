<template>
  <div class="relative mt-[100px]">
    <div class="sm:pt-[100px] pt-[30px] sm:pb-[80px] pb-[50px]">
      <section class="d-container">
        <div class="sm:pt-[0] pt-[50px]">
          <h1
            :class="`relative capitalize sm:pt-[40px] pt-[0px] sm:pb-[70px] pb-[35px] lg:text-[48px] sm:text-[32px] text-[26px] font-bold text-center bg-clip-text text-[#333]`"
          >
            How can we <span class="text-[#3B57F4]">help</span> you
          </h1>
          <div
            class="flex sm:flex-row flex-col sm:space-y-0 space-y-6 space-x-[20px] lg:pb-[50px] sm:pb-[50px] pb-[40px]"
          >
            <div class="lg:w-[50%] md:w-[65%] w-[100%]">
              <h1
                :class="`lg:text-[48px] text-[#3B57F4] sm:text-[32px] text-[20px] font-bold pb-[32px]`"
              >
                {{ data?.agency_wizard.contact.help.help_headline || 'Empowering helper'}}
              </h1>
              <p class="sm:text-[16px] text-[14px] pb-3" v-html="data?.agency_wizard.contact.help.help_desc">
                
              </p>
              <button
                :class="`py-3 px-6 bg-[#3B57F4] rounded-full text-white mt-[20px]`"
              >
                Contact Us
              </button>
            </div>
            <div class="md:w-[50%] w-[100%] relative">
              <img
                class="w-full"
                src="/images/smiling_help_guy.png"
                alt="illustration"
              />
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup lang="ts">
import { WizardResponse } from "../../type";
defineProps<{ data?: WizardResponse }>();
</script>

<style scoped></style>
