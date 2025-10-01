<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('Heads Or Tails is a simple game that is based on chance.') }}
      {{ $t('This game involves predicting the result of a flip of a coin.') }}
      {{ $t('This means that you have a fifty – fifty chance to win.') }}
    </p>
    <p>
      {{ $t('If you win your payout will be calculated as bet x {0}, otherwise you will lose your bet.', [this.payout]) }}
    </p>
  </div>
</template>

<script>
import { config } from '~/plugins/config'
import { round } from '~/plugins/utils'

export default {
  data () {
    return {
      infoTab: 'tab-about'
    }
  },

  computed: {
    payout () {
      return round(2 - config('heads-or-tails.house_edge') / 100, 2)
    }
  }
}
</script>
