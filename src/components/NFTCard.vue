<template>
  <div class="my-5">
    <div class="nes-container is-dark with-title">
      <p class="title">{{ nft.externalMetadata.name }}</p>

      <div class="flex flex-col w700:flex-row">
        <img :alt="nft.mint" :src="nft.externalMetadata.image">

        <div class="w700:ml-5 ml-0 mt-5 w700:mt-0 w500:text-base text-sm">
          <div class="flex flex-row">
            <div v-if="nft.soldAt" class="p-1 mb-2 bg-gray-600 width">Sold</div>
            <div v-else class="p-1 mb-2 text-black bg-rb-blue width">HODLing</div>
            <a class="ml-5" :href="`https://explorer.solana.com/address/${nft.mint}`" target="_blank">🔗</a>
          </div>

          <p v-if="nft.boughtAt" class="text">Bought for: <span class="text-rb-blue">{{ isSol ? '◎' : '$' }}{{ f(nft.boughtAt) }}</span></p>
          <p v-if="nft.soldAt" class="text">Sold for: <span class="text-rb-blue">{{ isSol ? '◎' : '$' }}{{ f(nft.soldAt) }}</span></p>
          <p v-if="nft.currentPrices" class="text">Current {{priceMethod}}: <span class="text-rb-blue">{{ isSol ? '◎' : '$' }}{{ f(nft.currentPrices[priceMethod]) }}</span></p>
          <p v-if="nft.profit" class="text">{{neg(nft.profit) ? 'Loss' : 'Profit'}} from sale: <span :class="neg(nft.profit) ? 'text-rb-pink' : 'text-rb-green'">{{ isSol ? '◎' : '$' }}{{ f(nft.profit) }}</span></p>
          <p v-if="nft.paperhanded" class="text">Paperhanded worth: <span :class="neg(nft.paperhanded[priceMethod]) ? 'text-rb-green' : 'text-rb-pink'">{{ isSol ? '◎' : '$' }}{{ f(nft.paperhanded[priceMethod]) }}</span></p>
          <p v-if="nft.diamondhanded" class="text">Diamondhanding worth: <span :class="neg(nft.diamondhanded[priceMethod]) ? 'text-rb-pink' : 'text-rb-green'">{{ isSol ? '◎' : '$' }}{{ f(nft.diamondhanded[priceMethod]) }}</span></p>
          <p v-if="!nft.currentPrices" class="text text-gray-400">This NFT collection is missing prices:( Fix by
            <a href="https://github.com/ilmoi/nftape.me#-important---adding-nft-collections" target="_blank">sending a PR</a> (~2min)</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import {f} from '@/common/util'

export default defineComponent({
  props: {
    nft: Object,
    priceMethod: String,
    isSol: Boolean,
  },
  setup() {
    const neg = (amount: number) => amount < 0
    return {neg, f}
  }
})
</script>

<style scoped>
img {
  max-width: 150px;
  max-height: 150px;
}
.text {
  text-align: left !important;
}
.width {
  width: 200px;
}
</style>
