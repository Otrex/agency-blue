<template>
  <div id="footer" class="bg-[#F0F3FF]">
    <div
      class="max-w-[1200px] mx-auto xl:px-[10px] lg:px-[30px] lg:px-[60px] md:px-[36px] px-[16px]"
    >
      <div
        class="py-[60px] w-full flex md:flex-row flex-col items-start justify-between"
      >
        <div class="xl:w-[40%] lg:w-[30%]">
          <img :src="data?.agency_wizard.website_details.logo || '/icons/logo.svg'" alt="Footer Logo" />
        </div>
        <div
          class="grid lg:grid-cols-3 md:grid-cols-2 items-start md:mt-[0] mt-[40px]"
        >
          <div
            class="md:text-[18px] text-[16px] md:mb-[0] mb-[32px] leading-[-1px]"
          >
            <p class="text-[#626262] mb-[4px]">Address</p>
            <p class="text-[#232323] font-[500] sm:pr-3">
              {{data?.agency_wizard.contact.address.address1 || '48180, Eureka Rd, Taylor, Michigan, USA'}}
            </p>
          </div>
          <div>
            <div
              class="md:text-[18px] text-[16px] md:mb-[0] mb-[32px] leading-[-1px]"
            >
              <p class="text-[#626262] mb-[4px]">Phone</p>
              <p class="text-[#232323] font-[500]">
                {{ data?.agency_wizard.contact.address?.phone || '(734) 287-6619'}}
              </p>
            </div>
            <div class="mt-[10px] md:text-[18px] text-[16px] leading-[-1px]">
              <p class="text-[#626262] mb-[4px]">Email</p>
              <a
                class="text-[#232323] font-[500]"
                href:mailto="{{ data?.agency_wizard.contact.address.email || 'info@agencyai.com'}}"
                >{{ data?.agency_wizard.contact.address.email || 'info@agencyai.com'}}</a
              >
            </div>
          </div>

          <div
            class="lg:mt-[0] md:mt-[40px] mt-[40px] flex items-center space-x-[26px]"
          >
          
            <a :href="data?.agency_wizard.contact.socials.facebook" target="_blank"> 
              <img src="/icons/brandico_facebook-rect_blue.svg" alt="facebook" />
            </a>
            <a :href="data?.agency_wizard.contact.socials.instagram" target="_blank"> 
              <img
                src="/icons/teenyicons_instagram-solid_blue.svg"
                alt="instagram"
              />
            </a>
            <a :href="data?.agency_wizard.contact.socials.youtube" target="_blank"> 
              <img src="/icons/mdi_twitter_blue.svg" alt="twitter" />
            </a>
            <a :href="data?.agency_wizard.contact.socials.linkedin" target="_blank"> 
              <img src="/icons/linkedIn_rect_blue.svg" alt="linkedIn" />
            </a>
          </div>
        </div>
      </div>

      <div class="py-[32px] border-t border-[#D4D4D4]">
        <p class="text-[#7D7D7D] md:text-[16px] text-[14px] text-center">
          © AgencyAi 2023. All rights reserved.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { WizardResponse } from '../../type';

defineProps<{ data?: WizardResponse }>();
</script>

<style></style>
