<template>
  <VCard class="pa-2 ma-4">
    <VRow>
      <VCol 
        v-for="n in 200" :key="n"
        cols="1" 
        sm="1"
      >
        <VHover v-slot="{ isHovering }">
          <VCard
            :elevation="isHovering ? 12 : 2"
           
            @click="copyURL(`https://picsum.photos/500/300?image=${n * 5 + 10}${isWithColor ? '' : '&grayscale'}`)"
          > <!-- Added the missing '>' closing tag here -->
            <v-img
              :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}&grayscale`"
              :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${isWithColor ? '' : '&grayscale'}`"
              aspect-ratio="1"
              class="bg-grey-lighten-2"
              cover
            >
              <template #placeholder>
                <VRow class="fill-height ma-0" align="center" justify="center">
                  <VProgressCircular
                    indeterminate
                    color="grey lighten-5"
                  ></VProgressCircular>
                </VRow>
              </template>
            </v-img>
          </VCard> <!-- Closing VCard correctly -->
        </VHover>
      </VCol>
    </VRow>
  </VCard>
</template>


<script>
export default {
  props: {
    isWithColor: {
      type: Boolean
    }
  },
  methods: {
    async copyURL(url) {
      try {
        await navigator.clipboard.writeText(url);
        console.log('URL copied to clipboard!');
         // Open the URL in a new tab
         window.open(url, '_blank');
      } catch (err) {
        console.error('Failed to copy: ', err);
      }
    }
  }
};
</script>

