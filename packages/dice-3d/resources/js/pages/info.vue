<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('The goal of the game is to predict which range the sum of points of all dice will fall into.') }}
      {{ $t('Scroll the slider to adjust the range.') }}
      {{ $t('Throw the dice by clicking "Play" button or holding the left mouse button and moving it in the direction of the throw.') }}
    </p>
    <p>
      {{ $t('The probability of winnings and win coefficient are in strict dependence of the winning chance and the width of the range.') }}
      {{ $t('It means that the probability of winning is higher when the range is wider and vice versa.') }}
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
