<template>
  <div>
    <h5>
      {{ $t('How to play') }}
    </h5>
    <p>
      {{ $t('Multiplayer roulette is similar to the regular roulette, except that the betting rounds last for a specific amount of time({ 0} seconds) and any player can place a bet during that time.', [duration]) }}
      {{ $t('Bets are accepted for red (pays bet x {0}), black (pays bet x {1}) and zero (pays bet x {2}).',[paytable.red, paytable.black, paytable.zero]) }}
      {{ $t('After completion of the betting round, the roulette spins and the winners are determined.') }}
    </p>
  </div>
</template>

<script>
import { config } from '~/plugins/config'

export default {
  data() {
    return {
      infoTab: 'tab-about',
      duration: parseInt(config('multiplayer-roulette.duration'), 10),
      paytable: config('multiplayer-roulette.paytable')
    }
  }
}
</script>
