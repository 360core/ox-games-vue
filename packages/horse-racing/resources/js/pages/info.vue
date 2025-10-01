<template>
  <div>
    <h5>
      {{ $t('How to play') }}
    </h5>
    <p>
              {{ $t('The objective of the game is to correctly guess which horse will finish in a place, i.e. finish first, second or third.') }}
              {{ $t('You can bet on several horses thus increasing your chances to win.') }}
            </p>
            <p>
              {{ $t('The following types of bets are supported:') }}
            </p>
            <ul>
              <li>
                {{ $t('Win — you win if your horse wins the race.') }}
              </li>
              <li>
                {{ $t('Place — you win if your horse finishes first or second.') }}
              </li>
              <li>
                {{ $t('Show — you win if your horse finishes first, second or third.') }}
              </li>
            </ul>
            <p></p>
            <p>
              {{ $t('Payouts are displayed to the right of the bet input field.') }}
              {{ $t('They differ depending on which bet and horse you choose.') }}
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
