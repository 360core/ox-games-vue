<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The American roulette wheel has 38 divisions with numbers from 1 to 36, single zero and double zero.') }}
      {{ $t('The objective of the game is to correctly guess the outcome of the roulette spin (the right number or the right group).') }}
    </p>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        infoTab: 'tab-about'
      }
    }
  }
</script>
