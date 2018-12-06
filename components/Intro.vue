<template>
  <div>
    <div 
      v-if="introIsPlaying" 
      ref="rwContainer"
      style="position: absolute;z-index:101; width:400px; left:-280px; top:-100px; height:100px;transform:translate(50vw, 50vh)">
      <svg 
        version="1.1" 
        xmlns="http://www.w3.org/2000/svg" 
        xmlns:xlink="http://www.w3.org/1999/xlink"             
        viewBox="0 0 322.96 90.83">
        <defs>
          <linearGradient 
            id="linear" 
            x1="0%" 
            y1="0%" 
            x2="100%" 
            y2="0%">
            <stop 
              offset="0%" 
              stop-color="#05a"/>
            <stop 
              offset="100%" 
              stop-color="#0a5"/>
          </linearGradient>
        </defs>
        
        <g fill="url(#linear)">      
          <path  
            ref="wLetter"                       
            d="M16.35,35.74H12.07V51.33H3.46V8.67H17.2q6.47,0,10,3.36t3.53,9.53q0,8.51-6.18,11.9L32,50.92v.41H22.76Zm-4.28-7.18H17a4.54,4.54,0,0,0,3.87-1.71,7.43,7.43,0,0,0,1.29-4.58q0-6.42-5-6.42h-5Z
          M36.24,11.43a4.3,4.3,0,0,1,1.23-3.17A4.43,4.43,0,0,1,40.75,7,4.43,4.43,0,0,1,44,8.26a4.3,4.3,0,0,1,1.23,3.17,4.51,4.51,0,1,1-9,0Zm8.7,39.9H36.62V19.63h8.32Z
          M62.81,45c2.4,0,3.63-1.56,3.66-4.69h7.8a11.65,11.65,0,0,1-3.2,8.38A10.82,10.82,0,0,1,63,51.91q-6.12,0-9.35-3.8T50.36,36.88V34.37c0-5,1.06-8.78,3.18-11.4S58.79,19,62.93,19a10.73,10.73,0,0,1,8.26,3.24q3,3.24,3.08,9.18h-7.8a8.31,8.31,0,0,0-.87-4.1,3,3,0,0,0-2.82-1.43,3.33,3.33,0,0,0-3.1,1.54q-.95,1.53-1,6v3.22a26.24,26.24,0,0,0,.38,5.41,4.15,4.15,0,0,0,1.26,2.25A3.85,3.85,0,0,0,62.81,45Z
          M87,22.41A8.21,8.21,0,0,1,93.66,19a7.69,7.69,0,0,1,6.59,3.05q2.27,3,2.29,9.08V51.33H94.22V31.26a7.19,7.19,0,0,0-.87-4A3.14,3.14,0,0,0,90.56,26,3.91,3.91,0,0,0,87,28.07V51.33H78.75v-45H87Z
          M150.44,35.48l4-26.81H163l-7.59,42.66h-8.64l-5-25.14-4.92,25.14H128.2L120.59,8.67h8.58l4,26.78,5-26.78h7.24Z
         M167.26,11.43a4.3,4.3,0,0,1,1.23-3.17,5,5,0,0,1,6.56,0,4.3,4.3,0,0,1,1.23,3.17,4.51,4.51,0,1,1-9,0Zm8.7,39.9h-8.32V19.63H176Z
          M191.07,51.33h-8.32v-45h8.32Z 
          M206.19,51.33h-8.32v-45h8.32Z
          M212.61,11.43a4.3,4.3,0,0,1,1.23-3.17,5,5,0,0,1,6.56,0,4.3,4.3,0,0,1,1.23,3.17,4.51,4.51,0,1,1-9,0Zm8.7,39.9H213V19.63h8.32Z
          M242.78,51.33a11.69,11.69,0,0,1-.7-2.46,7.09,7.09,0,0,1-6,3,8.92,8.92,0,0,1-6.6-2.63,9.27,9.27,0,0,1-2.62-6.83,9.58,9.58,0,0,1,3.18-7.7c2.11-1.82,5.17-2.75,9.15-2.79h2.52V29.41a4.74,4.74,0,0,0-.73-3,2.62,2.62,0,0,0-2.14-.88q-3.11,0-3.11,3.63H227.4a9.16,9.16,0,0,1,3.3-7.25A12.28,12.28,0,0,1,239,19c3.48,0,6.17.91,8.07,2.71S250,26.14,250,29.5V44.41a15.65,15.65,0,0,0,1.17,6.42v.5Zm-4.89-5.92a4.61,4.61,0,0,0,2.34-.56,3.93,3.93,0,0,0,1.44-1.31v-6.6h-2a4.25,4.25,0,0,0-3.33,1.35,5.18,5.18,0,0,0-1.21,3.6C235.14,44.24,236.05,45.41,237.89,45.41Z
          M263.76,19.63l.23,2.93A8.92,8.92,0,0,1,271.35,19a6.85,6.85,0,0,1,6.71,4.28A8.68,8.68,0,0,1,285.82,19q8.32,0,8.53,11.52V51.33h-8.3V31.08a7.49,7.49,0,0,0-.76-3.92A2.83,2.83,0,0,0,282.71,26c-1.54,0-2.69.94-3.45,2.84l.06,1V51.33H271V31.14a8,8,0,0,0-.74-3.94,2.78,2.78,0,0,0-2.6-1.21,3.8,3.8,0,0,0-3.4,2.31v23H256V19.63Z
          M314.5,42.83a2.58,2.58,0,0,0-1-1.95,19.84,19.84,0,0,0-4.5-2.41q-5.12-2.09-7-4.31A8.17,8.17,0,0,1,300,28.62a8.86,8.86,0,0,1,3-6.87A11.47,11.47,0,0,1,311,19a12.36,12.36,0,0,1,8.35,2.7A9.06,9.06,0,0,1,322.47,29h-8.29q0-3.86-3.22-3.86a2.87,2.87,0,0,0-3,3.1,2.37,2.37,0,0,0,.94,1.86,20.12,20.12,0,0,0,4.42,2.3q5.07,1.88,7.16,4.18a8.49,8.49,0,0,1,2.1,6,8.37,8.37,0,0,1-3.19,6.83A13,13,0,0,1,311,51.91a13.34,13.34,0,0,1-6.16-1.36,10.4,10.4,0,0,1-4.17-3.79,9.74,9.74,0,0,1-1.51-5.25H307a5.08,5.08,0,0,0,1,3.26,4,4,0,0,0,3.12,1.08Q314.51,45.85,314.5,42.83Z"/>        
      </g></svg>
    </div>
    <svg 
      v-if="introIsPlaying" 
      ref="panelsSvg"
      version="1.1" 
      xmlns="http://www.w3.org/2000/svg" 
      xmlns:xlink="http://www.w3.org/1999/xlink" 
      x="0px" 
      y="0px"      
      style="position:absolute; top:0; left:0; z-index:100"
      width="100%" 
      height="100%">     
      <rect 
        ref="introWhiteRec"
        width="100%"
        height="100%"
        fill="white"                          
      />
      <rect 
        ref="introBlackRec"
        width="100%"
        height="100%"
        fill="black"         
      />                 
    </svg>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timeline: null,
      introIsPlaying: true
    }
  },
  mounted() {
    const introWhiteRec = this.$refs.introWhiteRec
    const introBlackRec = this.$refs.introBlackRec
    const rwContainer = this.$refs.rwContainer
    const that = this
    this.timeline = new TimelineLite({
      onComplete: function() {
        that.introIsPlaying = false
        that.$emit('introComplete')
      }
    })
    this.timeline
      .to(introBlackRec, 1, {
        scaleY: 0.1,
        ease: Expo.easeIn
      })
      .to(introBlackRec, 1, {
        scaleY: 1,
        scaleX: 0.2,
        ease: Expo.easeIn
      })
      .to(introBlackRec, 1, {
        scaleY: 0.2,
        scaleX: 1,
        yPercent: 80,
        ease: Expo.easeIn
      })
      .to(introBlackRec, 1, {
        scaleY: 1,
        yPercent: 0,
        ease: Expo.easeIn
      })
      .staggerTo(
        '#linear stop',
        4,
        {
          stopColor: '#05a',
          cycle: {
            stopColor: ['#dbe122', '#6d6f71', '#7d7f71', '#ecf122']
          }
        },
        0.1,
        0
      )
      .to(rwContainer, 1, {
        scale: 1.5,
        transformOrigin: '0p 0px',
        ease: Elastic.easeInOut
      })
      .to(rwContainer, 1, {
        rotation: 1080,
        scale: 500,
        transformOrigin: '50% 50%',
        ease: Elastic
      })
      .staggerTo(
        '#linear stop',
        4,
        {
          stopColor: '#05a',
          cycle: {
            stopColor: ['#ffffff']
          }
        },
        0.1,
        0
      )
      .to(introBlackRec, 0.8, {
        opacity: 0,
        ease: Expo.easeIn
      })
      .to(
        introWhiteRec,
        1,
        {
          opacity: 0,
          ease: Expo.easeIn
        },
        '-=1.0'
      )
      .to(
        rwContainer,
        0.8,
        {
          opacity: 0,
          ease: Expo.easeIn
        },
        '-=1.0'
      )
  },
  methods: {}
}
</script>
