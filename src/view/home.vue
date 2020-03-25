<template>
  <div>
    <section onclick="judgeJump('Winter')" @click="judgeJump('Winter')" class="section">
      <h2 class="title">Winter</h2>
    </section>
    <section @click="judgeJump('Spring')" class="section">
      <h2 class="title">Spring</h2>
    </section>
    <section  @click="judgeJump('Summer')" class="section">
      <h2 class="title">Summer</h2>
    </section>
    <section  @click="judgeJump('Autumn')" class="section">
      <h2 class="title">Autumn</h2>
    </section>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      msg: 'chen yue lun +1'
    }
  },
  methods: {
    judgeJump (season) {
      console.log('11111111')
      switch (season) {
        case 'Winter':
          this.$router.push('winter')
          break
        case 'Spring':
          break
        case 'Summer':
          break
        case 'Autumn':
          break
      }
    }
  }
}
</script>
<style>
  @import url('https://fonts.googleapis.com/css?family=Permanent+Marker&display=swap');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: 'Permanent Marker', cursive;
  }
  img{
    width: 100%;
  }
  .section {
    align-items: center;
    background: url('../assets/images/timg.jpeg') no-repeat center / cover;
    bottom: 0;
    display: flex;
    justify-content: center;
    height: 100vh;
    padding: 1rem;
    position: sticky;
    width: 100%;
    z-index: -1;
  }

  .section:nth-child(2) {
    background: url('../assets/images/timg2.jpeg') no-repeat center / cover;
    z-index: -2;
  }

  .section:nth-child(3) {
    background:  url('../assets/images/timg3.jpeg') no-repeat center / cover;
    z-index: -3;
  }

  .section:last-child {
    background-image: url('../assets/images/timg4.jpeg');
    z-index: -4;
  }

  .title {
    color: #FFF;
    font-size: 5rem;
    text-stroke: 0.1px #000;
    -webkit-text-stroke: 1px #000;
  }

  @supports not (-webkit-text-stroke: 1px #000) {
    .title {
      text-shadow:
        3px  3px 0 #000,
        -1px -1px 0 #000,
        1px -1px 0 #000,
        -1px  1px 0 #000,
        1px  1px 0 #000;
    }
  }
</style>
