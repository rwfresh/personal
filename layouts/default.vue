<template>
  <div>
    <intro @introComplete="introCompleted" />
    <section>
      <nav 
        ref="navbar"
        class="navbar is-spaced"
        role="navigation" 
        aria-label="main navigation">
        <div class="container">
          <div class="navbar-brand">
            <a
              class="navbar-item" 
              href="/">
              <wifi-logo v-if="showLogo" />
            </a>            
            <div class="navbar-burger">
              <span/>
              <span/>
              <span/>
            </div>
          </div>         
          <div class="navbar-end">                        
            <a 
              href="" 
              class="button is-rounded is-outlined mrs flip-in-hor-bottom">design</a>
            <a 
              href="" 
              class="button is-rounded is-outlined mrs flip-in-hor-bottom">architect</a>
            <a 
              href="" 
              class="button is-rounded is-outlined mrs flip-in-hor-bottom">deliver</a>           
          </div>
       
        </div>
      </nav>
    </section>
    <section class="main-content columns">
      <div class="container column is-12">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import wifiLogo from '@/components/WifiLogo'
import intro from '@/components/Intro'

export default {
  components: { wifiLogo, intro },
  data() {
    return {
      showLogo: false
    }
  },
  mounted() {},
  methods: {
    introCompleted() {
      this.showLogo = true
    }
  }
}
</script>
<style>
html {
  height: 100%;
}

.flip-in-hor-bottom {
  -webkit-animation: flip-in-hor-bottom 0.5s
    cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
  animation: flip-in-hor-bottom 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
}

@-webkit-keyframes flip-in-hor-bottom {
  0% {
    -webkit-transform: rotateX(80deg);
    transform: rotateX(80deg);
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateX(0);
    transform: rotateX(0);
    opacity: 1;
  }
}
@keyframes flip-in-hor-bottom {
  0% {
    -webkit-transform: rotateX(80deg);
    transform: rotateX(80deg);
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateX(0);
    transform: rotateX(0);
    opacity: 1;
  }
}

.navbar-link {
  color: #6d6f71 !important;
}
</style>
