<template>
  <main>
    <BaseHeaderThree :data="state" />
    <Type2HeroT2 :data="state"/>
    <Type2HelpYouT2 :data="state"/>
    <SharedOurServices :data="state" :header-text-color="'text-[#3B57F4]'" titleColor="text-[#000]"/>
    <SharedBenefits :data="state" :header-text-color="'text-[#232323]'"/>
    <SharedAboutUs :data="state" :image="'/images/about_team_2.png'" :header-text-color="'text-[#232323]'" :button-bg="'bg-[#3B57F4]'" />
    <SharedReviews :data="state" :header-text-color="'text-[#000]'" />
    <BaseMainFooterTwo />
  </main>
</template>

<script setup lang="ts">
import axios from "axios";
import { WizardResponse } from "../type";

const state = ref<WizardResponse>();
const config = useRuntimeConfig();
const route = useRoute();

onMounted(async () => {
  try {
    const result = await axios.get(`${config.public.baseURL}/d/${route.params.workspaceId}/wizard`);
    const data = result.data as WizardResponse;

    state.value = data;
  } catch (error) {
    navigateTo("/")
  }
})

definePageMeta({
  layout: false,
});
</script>

<style></style>
