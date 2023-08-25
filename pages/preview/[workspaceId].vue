<template>
  <transition name="fade" mode="out-in">
    <div class="w-full h-screen flex items-center justify-center" v-if="!state">
      <div class="loading-circle"></div>
    </div>
    <main v-else>
      <BaseSeo />
      <BaseHeaderThree :data="state" />
      <Type2HeroT2 :data="state" />
      <Type2HelpYouT2 :data="state" />
      <SharedOurServices
        :data="state"
        :header-text-color="'text-[#3B57F4]'"
        titleColor="text-[#000]"
      />
      <SharedBenefits :data="state" :header-text-color="'text-[#232323]'" />
      <SharedAboutUs
        :data="state"
        :image="'/images/about_team_2.png'"
        :header-text-color="'text-[#232323]'"
        :button-bg="'bg-[#3B57F4]'"
      />
      <SharedReviews :data="state" :header-text-color="'text-[#000]'" />
      <BaseMainFooterTwo :data="state" />
    </main>
  </transition>
</template>

<script setup lang="ts">
import axios from "axios";
import { WizardResponse } from "../../type";

const state = ref<WizardResponse>();
const config = useRuntimeConfig();
const route = useRoute();

definePageMeta({
  layout: false,
});

onMounted(async () => {
  try {
    const result = await axios.get(
      `${config.public.baseURL}/d/${route.params.workspaceId}/wizard`,
    );

    const data = result.data as WizardResponse;

    state.value = data;
  } catch (error) {
    navigateTo("/404");
  }
});

useHead(() => ({
  title: state.value?.agency_wizard.seo.title || "Welcome to Agency Pages",
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: state.value?.agency_wizard.website_details.favIcon,
    },
  ],
  script: [
    {
      innerHTML:
        state.value?.agency_wizard.website_details.customJavascript || "null",
      type: "text/javascript",
    },
  ],
}));
</script>

<style></style>
