<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The game generates a random number in a range from 0 to 9999 and compares to the range or numbers set by you.') }}
      {{ $t('If the result roll number falls into that range you win, otherwise you lose.') }}
    </p>
    <p>
      {{ $t('The probability of winnings and win coefficient are in strict dependence of the winning chance and the width of the range.') }}
      {{ $t('It means that the probability of winning is higher when the range is wider and vice versa.') }}
    </p>
    <p>
      {{ $t('To start a game you can either specify a comfortable win chance or set the payout you would like to receive if you win.') }}
      {{ $t('Other parameters will be adjusted automatically.') }}
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
