<template>
  <circle 
    cx="cx" 
    cy="cy" 
    r="r"/>
</template>
<script>
export default {
  props: {
    cx: { type: Number, default: 10 },
    cy: { type: Number, default: 0 },
    r: { type: Number, default: 10 }
  },
  data() {
    return {}
  }
}
</script>
