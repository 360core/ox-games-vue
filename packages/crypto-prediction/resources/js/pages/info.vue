<template>
  <div class="game-info">
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The objective of this game is to correctly predict whether the price of a certain coin will go up or down.') }}
    </p>
    <p>
      {{ $t('To play the game select a coin, duration (period) and bet amount.') }}
    </p>
    <p>
      {{ $t('If you think the price will rise from the current price level, click "Higher".') }}
      {{ $t('Otherwise, if you think the price will drop from the current price level, click "Below".') }}
    </p>

    <h5>{{ $t('Paytable') }}</h5>
    <table>
      <thead>
        <tr>
          <th>{{ $t('Bet type') }}</th>
          <th>{{ $t('Payout') }}</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{ $t('Higher') }}</td>
          <td>{{ higherPayout }}</td>
        </tr>
        <tr>
          <td>{{ $t('Lower') }}</td>
          <td>{{ lowerPayout }}</td>
        </tr>
      </tbody>
    </table>

    <h5>{{ $t('Assets') }}</h5>
    <table>
      <thead>
        <tr>
          <th>#</th>
          <th>{{ $t('Symbol') }}</th>
          <th>{{ $t('Name') }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(asset, i) in assets" :key="asset.id">
          <td>{{ i + 1 }}</td>
          <td>{{ asset.symbol }}</td>
          <td>{{ asset.name }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'
import { config } from '~/plugins/config'
import { route } from '~/plugins/route'

export default {
  data () {
    return {
      assets: []
    }
  },

  computed: {
    higherPayout () {
      return config('crypto-prediction.paytable')[1]
    },
    lowerPayout () {
      return config('crypto-prediction.paytable')[-1]
    }
  },

  async created () {
    const { data: assets } = await axios.post(route('assets.search'), { type: 'crypto', search: '', exact: false })
    this.assets = assets
  }
}
</script>

<style scoped>
.game-info {
  padding: 20px;
}

h5 {
  margin-top: 24px;
  font-size: 1.2rem;
  font-weight: 600;
}

p {
  margin-bottom: 10px;
  line-height: 1.5;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}

table th, table td {
  border: 1px solid #ddd;
  padding: 8px;
}

table th {
  background-color: #f5f5f5;
  text-align: left;
}
</style>
