<template> 
  <div>
    <img :src="data?.agency_wizard.website_details.favIcon" />
  </div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '../../type';

defineProps<{ data?: WizardResponse }>();
</script>

<style> 
    
</style>