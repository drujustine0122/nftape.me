<template>
  <nav class="flex flex-row justify-center align-middle rainbow-bg">
    <a class="menu-item text-2xl self-center" href="https://www.nftarmory.me/view" target="_blank">⚔️</a>
    <h1 class="menu-item bg-none text-black text-2xl self-center">NFT<span class="text-3xl">🍌</span>APE</h1>
    <a class="menu-item text-2xl self-center" href="https://github.com/ilmoi/awesome-solana-nfts" target="_blank">🔗</a>
  </nav>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent( {
  setup() {
    return {

    }
  }
})
</script>

<style scoped>
.menu-item {
  @apply px-10 py-3;
}

.rainbow-bg{
		animation: rainbow-bg 30s linear;
		animation-iteration-count: infinite;
}

@keyframes rainbow-bg{
		100%,0%{
			background-color: rgb(255,255,0);
		}
		8%{
			background-color: rgb(127,255,0);
		}
		16%{
			background-color: rgb(0,255,0);
		}
		25%{
			background-color: rgb(0,255,127);
		}
		33%{
			background-color: rgb(0,255,255);
		}
		41%{
			background-color: rgb(0,127,255);
		}
		50%{
			background-color: rgb(0,0,255);
		}
		58%{
			background-color: rgb(127,0,255);
		}
		66%{
			background-color: rgb(255,0,255);
		}
		75%{
			background-color: rgb(255,0,127);
		}
		83%{
      background-color: rgb(255,0,0);
		}
		91%{
      background-color: rgb(255,127,0);
		}
}

@keyframes rainbow{
		100%,0%{
			color: rgb(255,255,0);
		}
		8%{
			color: rgb(127,255,0);
		}
		16%{
			color: rgb(0,255,0);
		}
		25%{
			color: rgb(0,255,127);
		}
		33%{
			color: rgb(0,255,255);
		}
		41%{
			color: rgb(0,127,255);
		}
		50%{
			color: rgb(0,0,255);
		}
		58%{
			color: rgb(127,0,255);
		}
		66%{
			color: rgb(255,0,255);
		}
		75%{
			color: rgb(255,0,127);
		}
		83%{
      color: rgb(255,0,0);
		}
		91%{
      color: rgb(255,127,0);
		}
}
</style>
