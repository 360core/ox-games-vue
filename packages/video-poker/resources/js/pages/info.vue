<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The objective of the game is to collect one of the possible winning combinations based on the 5-card draw.') }}
    </p>
    <p>
      {{ $t('In the first round you receive 5 random cards.') }}
      {{ $t('You can then exchange any one of the received cards (or all of them) for another in order to collect a winning combination.') }}
      {{ $t('To keep a specific card click on it and it will be held during the second draw.') }}
    </p>

    <h5>{{ $t('Paytable') }}</h5>
    <table>
      <thead>
        <tr>
          <th>{{ $t('Result') }}</th>
          <th>{{ $t('Payout') }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(payout, i) in paytable" :key="i">
          <td>{{ combinations[i] }}</td>
          <td>{{ $t('bet') }} x {{ payout }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { config } from '~/plugins/config'

export default {
  data () {
    return {
      infoTab: 'tab-about',
      paytable: config('video-poker.paytable').slice(1),
      combinations: [
        this.$t('Pair (jacks or better)'),
        this.$t('Two pair'),
        this.$t('Three of a kind'),
        this.$t('Straight'),
        this.$t('Flush'),
        this.$t('Full house'),
        this.$t('Four of a kind'),
        this.$t('Straight flush'),
        this.$t('Royal flush')
      ]
    }
  }
}
</script>
