<template>
  <div>
    <h5>{{ $t('How to play') }}</h5>
    <p>
      {{ $t('Make a bet and spin the wheel.') }}
      {{ $t('You will win or lose depending on which section the pointer will land after the wheel stops.') }}
    </p>

  </div>
</template>

<script>
export default {
  data() {
    return {
      infoTab: 'tab-about'
    }
  }
}
</script>
