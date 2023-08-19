<template>
  <main>
    <BaseHeaderThree />
    <Type2HeroT2/>
    <Type2HelpYouT2/>
    <SharedOurServices :header-text-color="'text-[#3B57F4]'" titleColor="text-[#000]"/>
    <SharedBenefits :header-text-color="'text-[#232323]'"/>
    <SharedAboutUs :image="'/images/about_team_2.png'" :header-text-color="'text-[#232323]'" :button-bg="'bg-[#3B57F4]'" />
    <SharedReviews :header-text-color="'text-[#000]'" />
    <BaseMainFooterTwo />
  </main>
</template>

<script setup lang="ts">
definePageMeta({
  layout: false,
});
</script>

<style></style>
