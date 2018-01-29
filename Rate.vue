<template>
  <div  v-bind:style="this.styleFont">
    <slot></slot>
    <div class='rate'>
      {{"☆".repeat(parseInt(length))}}
      <span v-bind:style="styleObject">{{"★".repeat(parseInt(length))}}</span>
    </div>

  </div>
</template>
<script>
export default {
  name: 'Rate',
  data: function () {
    const themeObj = {
      'black': '#00',
      'white': '#fff',
      'red': '#f5222d',
      'orange': '#fa541c',
      'yellow': '#fadb14',
      'green': '#73d13d',
      'blue': '#40a9ff',
      'purple': '#9254de'
    }
    return {
      styleObject: {},
      styleFont: {
        color: themeObj[this.theme] ? themeObj[this.theme] : this.theme,
        fontSize: this.size ? this.size : ''
      }
    }
  },
  props: {
    value: {type: [Number, String], default: '0'},
    length: {type: [Number, String], default: '5'},
    animate: {type: [Number, String], default: '0'},
    theme: {type: [String], default: 'yellow'},
    size: {type: [String]}
  },
  methods: {
    setStyle: function () {
      this.styleObject = {
        width: this.value + 'em',
        transition: `width ${this.animate}s`
      }
    }
  },
  created: function () {
    if (this.animate === '0' || this.animate === 0) {
      this.setStyle()
    }
    setTimeout(() => {
      this.setStyle()
    })
  }
}
</script>

<style scoped>
.rate{
  position:relative;
  display: inline-block;
}
.rate span {
  position:absolute;
  display: inline-block;
  top:0;
  left:0;
  width:0;
  overflow:hidden;
}

</style>
