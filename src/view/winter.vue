<template>
 <div>
   <div class="diy-slideshow">
     <figure :class="{'show' : counter == 0}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/snowying.jpg" width="100%" /><figcaption>"Snowying" by <a href="http://www.flickr.com/photos/fiddleoak/8511209344/">fiddleoak</a>.</figcaption>
     </figure>
     <figure :class="{'show' : counter == 1}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/starlight.jpg" width="100%" /><figcaption>"Starlight" by <a href="http://www.flickr.com/photos/chaoticmind75/10738494123/in/set-72157626146319517">ChaoticMind75</a>.</figcaption>
     </figure>
     <figure :class="{'show' : counter == 2}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/snowstorm.jpg" width="100%" /><figcaption>"Snowstorm" by <a href="http://www.flickr.com/photos/tylerbeaulawrence/8539457508/">Beaulawrence</a>.</figcaption>
     </figure>
     <figure :class="{'show' : counter == 3}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/misty-winter-afternoon.jpg" width="100%" /><figcaption>"Misty winter afternoon" by <a href="http://www.flickr.com/photos/22746515@N02/5277611659/">Bert Kaufmann</a>.</figcaption>
     </figure>
     <figure :class="{'show' : counter == 4}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/good-morning.jpg" width="100%" /><figcaption>"Good Morning!" by <a href="http://www.flickr.com/photos/frank_wuestefeld/4306107546/">Frank Wuestefeld</a>.</figcaption>
     </figure>
     <figure :class="{'show' : counter == 5}">
       <img src="http://themarklee.com/wp-content/uploads/2013/12/driving-home-for-christmas.jpg" width="100%" /><figcaption>"Driving home for Christmas" by <a href="http://www.flickr.com/photos/22746515@N02/5292186041/">Bert Kaufmann</a>.</figcaption>
     </figure>
     <span class="prev" @click="pre">&laquo;</span>
     <span class="next" @click="next">&raquo;</span>
   </div>

   <p>An example of a pretty basic diy slideshow. This is the no-jQuery version.</p>
 </div>
</template>

<script>
export default {
  name: 'winter',
  data () {
    return {
      counter: 0 // to keep track of current slide
    }
  },
  methods: {
    next () {
      let nextCounter = this.counter + 1
      if (nextCounter > 5) {
        nextCounter = 0
      }
      this.counter = nextCounter
    },
    pre () {
      let preCounter = this.counter - 1
      if (preCounter < 0) {
        preCounter = 5
      }
      this.counter = preCounter
    }
  }
}
</script>

<style scoped>
  body {
    margin: 0;
    padding: 0;
    background: #111;
    height: 100%;
  }
  .diy-slideshow{
    position: relative;
    display: block;
    overflow: hidden;
  }
  figure{
    position: absolute;
    opacity: 0;
    transition: 1s opacity;
  }
  figcaption{
    position: absolute;
    font-family: sans-serif;
    font-size: .8em;
    bottom: .75em;
    right: .35em;
    padding: .25em;
    color: #fff;
    background: rgba(0,0,0, .25);
    border-radius: 2px;
  }
  figcaption a{
    color: #fff;
  }
  figure.show{
    opacity: 1;
    position: static;
    transition: 1s opacity;
  }
  .next, .prev{
    color: #fff;
    position: absolute;
    background: rgba(0,0,0, .6);
    top: 50%;
    z-index: 1;
    font-size: 2em;
    margin-top: -.75em;
    opacity: .3;
    user-select: none;
  }
  .next:hover, .prev:hover{
    cursor: pointer;
    opacity: 1;
  }
  .next{
    right: 0;
    padding: 10px 5px 15px 10px;
    border-top-left-radius: 3px;
    border-bottom-left-radius: 3px;
  }
  .prev{
    left: 0;
    padding: 10px 10px 15px 5px;
    border-top-right-radius: 3px;
    border-bottom-right-radius: 3px;
  }
  p{
    margin: 10px 20px;
    color: #fff;
  }
</style>
