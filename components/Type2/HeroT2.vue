

<template>
  <main id="quote">
    <section
      class="op-hero xl:pt-[130px] lg:pt-[140px] md:pt-[120px] pt-[115px] -mt-[80px]"
    >
      <div
        class="font_jakarta max-w-[1200px] mx-auto xl:px-[10px] lg:px-[60px] md:px-[24px] sm:px-[80px] pb-[200px]"
      >
        <div class="w-full flex md:flex-row flex-col gap-[3rem] items-center">

          <div class="md:text-left w-full text-center px-[20px]">
            <h2
              class="font-[800] capitalize xl:text-[50px] lg:text-[40px] sm:text-[30px] text-[24px] text-[#3B57F4] mb-[24px]"
            >
              {{data?.agency_wizard.contact.introduction.intro_headline || 'Unleash Your Brand Potential WIth Marketing Done Right'}}
            </h2>
            <p
              class="font-[400] xl:text-[28px] lg:text-[24px] smtext-[20px] text-[16px] text-[#232323] leading-[-1.4px]"
            v-html="data?.agency_wizard.contact.introduction.intro_desc || 'Leverage our Exceptional Services to boost your Online Business growth.'">
            </p>
            <button
              class="md:mt-[48px] mt-[60px]
              rounded-full md:px-[60px] px-[40px] md:py-[22px] py-[18px] bg-[#3B57F4] text-[20px] text-[#fff]"
              @click="linkTo(data?.agency_wizard.contact.introduction.intro_cta_button_link || '')"
            >
              Get Started
            </button>
          </div>

          <div class="md:order-2 w-full order-1">
            <iframe
              class="w-full aspect-video rounded-[2rem]"
              title="Neve 2.0: Introducing the Header and Footer Builder [NEW]"
              :data-src="data?.agency_wizard.contact.introduction.intro_video_url || 'https://www.youtube.com/embed/s_o9v2EatW8?feature=oembed'"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              :src="data?.agency_wizard.contact.introduction.intro_video_url || 'https://www.youtube.com/embed/s_o9v2EatW8?feature=oembed'"
              vnb-frameid="4576"
            ></iframe>
            <!-- <img
              class="w-full"
              src="/images/hero_img_3.png"
              alt="illustration"
            /> -->
          </div>

        </div>
      </div>
    </section>
    <div class="relative bg-gradient-to-b from-[#F0F3FF] to-[#fff]">
      <Type2QuoteT2 :data="data" />
    </div>
  </main>
</template>

<script setup lang="ts">
import { WizardResponse } from "../../type";

defineProps<{ data?: WizardResponse }>();
</script>

<style scoped>
.op-hero {
  background: #f0f3ff;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  max-height: 150vh;
  height: 100%;
}
</style>
