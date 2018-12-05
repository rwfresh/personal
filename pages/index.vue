<template>
  <section class="section">        
    <div 
      class="content has-text-centered" 
      style="width:100%; height:500px; position:fixed">            
      <svg 
        version="1.1"
        xmlns="http://www.w3.org/2000/svg" 
        xmlns:xlink="http://www.w3.org/1999/xlink" 
        x="0px" 
        y="0px" 
        width="100%"
        height="100%" 
        viewBox="0 0 100 100"
        xml:space="preserve"               
        @mouseover="spinFlower"
        @mouseout="stopFlower">
        <defs>
          <clipPath 
            v-for="clips in circleClips" 
            :id="clips.id"
            :key="clips.id" 
            stroke-width="1.5" 
            stroke="#000">
            <circle                     
              :r="clips.r"
              :cx="clips.cx"
              :cy="clips.cy"
              :transform="clips.transform"
              stroke-width="1.5" 
              stroke="#000"
              fill="none" />
          </clipPath>                
        </defs>
        <g           
          ref="flowerClip"                 
          transform="translate(45,40)">
          <circle 
            v-for="circle in circles" 
            :key="circle.circId" 
            :r="circle.r" 
            :cy="circle.cy" 
            :cx="circle.cx"                  
            :fill="circle.fill"                   
            :clip-path="circle.clipPath"
            :transform="circle.transform"                  
          />
        </g>
        <g           
          ref="flowerCircle"
          transform="translate(45,40)">                                
          <circle 
            v-for="circle in circles" 
            :key="circle.circId" 
            :r="circle.r" 
            :cy="circle.cy" 
            :cx="circle.cx"                  
            :transform="circle.transform"                   
            fill="none"
            stroke-width=".5"
            stroke="#DADADA" 
          />
        </g>
      </svg>
    </div>
    <div style="width:100%; height:500px"/>
    <div style="height:20px;"/>
    <div ref="testTrigger">asdfasdf</div>
    <div style="height:400px;"/>
  </section>
</template>

<script>
import SvgCircle from '@/components/SvgCircle'
import { TimelineLite } from 'gsap'

export default {
  name: 'HomePage',
  components: { SvgCircle },
  data() {
    return {
      scrollTimeline: null,
      timeline: null,
      scrollCtrl: null,
      circleClips: [
        {
          id: 'mask_b',
          cx: 10,
          cy: 0,
          r: 10,
          transform: 'rotate(120,0,0)'
        }
      ],
      circles: [
        {
          cx: 0,
          cy: 0,
          r: 10,
          fill: 'none',
          circId: 'a'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          circId: 'b',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(60, 0, 0)',
          circId: 'c',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(120, 0, 0)',
          circId: 'd',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(180, 0, 0)',
          circId: 'e',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(240, 0, 0)',
          circId: 'f',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(300, 0, 0)',
          circId: 'g',
          clipPath: 'url(#mask_b)'
        }
      ]
    }
  },
  mounted() {
    this.animateHome()
  },
  methods: {
    spinFlower() {
      if (this.timeline.progress() == 1) {
        this.timeline.restart()
      } else {
        this.timeline.resume()
      }
    },
    stopFlower() {
      this.timeline.pause()
    },
    animateHome() {
      this.timeline = new TimelineLite()
      this.timeline.to(this.$refs.flowerCircle, 3, {
        rotation: 360,
        transformOrigin: '50% 50%'
      })

      const flowerClip = this.$refs.flowerClip
      const flowerCircle = this.$refs.flowerCircle
      this.scrollTimeline = new TimelineLite()
      this.scrollTimeline
        .to(flowerClip, 1, {
          scale: 0.1,
          rotation: 720,
          opacity: 0,
          transformOrigin: '0% 0%',
          skewX: 45
        })
        .to(flowerClip, 3, {
          x: 45,
          y: 40,
          skewX: 0,
          opacity: 1,
          scale: 1,
          rotation: -720
        })
        .to(flowerClip, 3, {
          rotation: 1080,
          transformOrigin: '50% 50%'
        })
        .to(
          flowerCircle,
          3,
          {
            rotation: 360,
            transformOrigin: '50% 50%'
          },
          '-=0.50'
        )
        .to(
          flowerCircle,
          3,
          {
            scale: 0.5
          },
          '-=0.50'
        )
        .to(
          flowerClip,
          3,
          {
            scale: 0.5
          },
          '-=1'
        )
        .to(flowerCircle, 3, {
          scale: 2
        })
        .to(
          flowerClip,
          3,
          {
            scale: 2
          },
          '-=3'
        )

      // use scrollmagic
      this.scrollCtrl = new this.$scrollmagic.Controller()
      let flowerScene = new this.$scrollmagic.Scene({
        triggerElement: this.$refs.testTrigger
      }).setTween(this.scrollTimeline)

      this.scrollCtrl.addScene([flowerScene])
    }
  }
}
</script>
<style>
</style>
