<template> 
<div class="h-[3rem]"> 
  &nbsp;
  <div class="fixed max-w-[60rem] ml-[5rem] mx-auto pt-[.4rem] top-0"> 
    <div class="flex gap-4 w-full justify-center items-center flex-row">
      <div class="flex text-bold gap-3 items-center"> 
        Favicon: <span class="inline-block w-[2rem] rounded-lg overflow-hidden bg-slate-300 aspect-square"><img class="w-full h-full object-cover" :src="data?.agency_wizard.website_details.favIcon" /></span>
      </div>
      <div class="text-bold">
        Title: <span> {{ data?.agency_wizard.seo.title }} </span>
      </div>
    </div>
  </div>

</div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '../../type';

defineProps<{ data?: WizardResponse }>();
</script>

<style> 
    
</style>