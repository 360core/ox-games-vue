<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The objective of the game is to get the symbols on the reels to fall in a perfect line.') }}
    </p>
    <h5>{{ $t('Reels') }}</h5>
    <div class="reels">
      <div v-for="reelIndex in [0,1,2]" :key="reelIndex" class="reel">
        <div v-for="(symbolIndex, index) in reels[reelIndex]" :key="index" class="symbol">
          <img :src="symbols[symbolIndex]" :alt="symbols[symbolIndex]" class="icon">
        </div>
      </div>
    </div>
    <h5>{{ $t('Paytable') }}</h5>
    <div class="paytable">
      <div v-for="(payline, paylineIndex) in paytable" :key="paylineIndex" class="payline">
        <span v-for="reelIndex in [0,1,2]" :key="reelIndex" class="symbol">
          <img
            v-if="payline.positions[reelIndex] !== null"
            :src="symbols[payline.positions[reelIndex]]"
            class="icon"
          >
          <span v-else class="any">{{ $t('Any') }}</span>
        </span>
        <span class="payout">
          {{ $t('pays x{0} credits', [payline.payout]) }}
        </span>
      </div>
    </div>

    
  </div>
</template>

<script>
import { config } from '~/plugins/config'

export default {
  data () {
    return {
      infoTab: 'tab-about'
    }
  },

  computed: {
    symbols () {
      return config('slots-3d.symbols')
    },
    reels () {
      return config('slots-3d.reels')
    },
    paytable () {
      return config('slots-3d.paytable')
    }
  }
}
</script>
<style scoped>
h5 {
  margin-top: 16px;
  margin-bottom: 8px;
  font-weight: bold;
}

.payline {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

.symbol {
  display: inline-block;
  margin-right: 8px;
}

.icon {
  width: 48px;
  height: 48px;
  object-fit: contain;
}

.any {
  font-weight: bold;
}

.payout {
  margin-left: 16px;
}

.reels {
  display: flex;
  gap: 20px;
  margin-top: 10px;
}

.reel {
  flex: 1;
  max-height: 300px;
  overflow-y: auto;
  text-align: center;
}

.reel .symbol {
  margin-bottom: 10px;
}
</style>