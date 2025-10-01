<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('Select {0} numbers from 1 to {1} by clicking on a specfic number.', [selectCount, max]) }}
      {{ $t('If it is too boring click "Random" button to generate numbers for you.') }}
      {{ $t('Choose your bet and click "Play".') }}
    </p>
    <p>
      {{ $t('{0} unique random numbers will be generated.', [drawCount]) }}
      {{ $t('The goal is to match as many numbers you chose on the board with the generated numbers as possible.') }}
    </p>

    <h5>{{ $t('Paytable') }}</h5>
    <table>
      <thead>
        <tr>
          <th>{{ $t('Number of matches') }}</th>
          <th>{{ $t('Payout') }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(payout, i) in paytable" :key="i" v-if="payout > 0">
          <td>{{ i + 1 }}</td>
          <td>{{ $t('bet') }} x {{ payout }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { config } from '~/plugins/config'

export default {
  data() {
    return {
      infoTab: 'tab-about'
    }
  },

  computed: {
    paytable() {
      return config('keno.paytable')
    },
    selectCount() {
      return parseInt(config('keno.select_count'), 10)
    },
    drawCount() {
      return parseInt(config('keno.draw_count'), 10)
    },
    max() {
      return parseInt(config('keno.rows_count'), 10) * parseInt(config('keno.cols_count'), 10)
    }
  }
}
</script>
