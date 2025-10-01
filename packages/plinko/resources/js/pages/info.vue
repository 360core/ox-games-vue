<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
              {{ $t('Plinko is a game of chance played with a ball falling down the vertical board in the form of a pyramid.') }}
              {{ $t('After you place a bet the ball will start bouncing through the obstacles from the top of the pyramid to the bottom.') }}
              {{ $t('At the end it will drop into a slot (bucket) with the corresponding payout.') }}
              {{ $t('The closer the ball ends up along the sides the bigger your win will be.') }}
              {{ $t('Trust your luck and let the ball fall!') }}
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
