<template>
  <!-- <WalletButton /> -->
  <CoinFlip />
</template>

<script>
import {
  PhantomWalletAdapter,
  //SolflareWalletAdapter 
} from '@solana/wallet-adapter-wallets';
import { initWallet } from 'solana-wallets-vue';
import CoinFlip from './components/CoinFlip.vue';
// import WalletButton from './components/WalletButton.vue';



// const wallets = [
//     new PhantomWalletAdapter(),
//     new SolflareWalletAdapter(),
// ];

// initWallet({ wallets, autoConnect: true });

export default {
  name: 'App',
  components: {
    CoinFlip,
    // WalletButton
  },
  setup() {
    console.log('Initializing wallet...');

    const walletOptions = {
      wallets: [
        new PhantomWalletAdapter()
      ],
      autoConnect: true,
    };

    initWallet(walletOptions);
  }
}


</script>

<style></style>
