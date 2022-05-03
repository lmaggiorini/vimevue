<template>
  <div>
    <Player id="vid" playsinline
            controls
            ref="player"
            @vmCurrentTimeChange="onTimeUpdate"
            @vmDurationChange="getDuration"
    >
      <!--          <Video poster="https://media.vimejs.com/poster.png">
                  &lt;!&ndash;
                        https://media.vimejs.com/720p.mp4
                        /media/sample.mp4
                  &ndash;&gt;
                  <source
                      data-src="https://media.vimejs.com/720p.mp4"
                      type="video/mp4"
                  />
                </Video>-->
      <Vimeo videoId="705401280"/>

    </Player>
  </div>
</template>

<script>

import {Player, Vimeo} from "@vime/vue-next";


export default {
  name: 'App',
  components: {Player, Vimeo},
  computed: {
    player() {
      return this.$refs.player;
    },
  },
  methods: {
    onTimeUpdate(ev) {
      console.log("onTimeUpdate", ev)
      console.log(this.player)
    },
    getDuration(ev) {
      console.log(ev)
    }
  },
  data() {
    return {}
  },


}
</script>

<style>
@import '@vime/core/themes/default.css';


</style>
