<template>
  <b-container class="bv-example-row bv-example-row-flex-cols">
    <no-ssr>
      <vue-particles
          color="#dedede"
          :particleOpacity="0.7"
          :particlesNumber="80"
          shapeType="circle"
          :particleSize="4"
          linesColor="#dedede"
          :linesWidth="1"
          :lineLinked="true"
          :lineOpacity="0.4"
          :linesDistance="150"
          :moveSpeed="3"
          :hoverEffect="true"
          hoverMode="grab"
          :clickEffect="true"
          clickMode="push"
        >
      </vue-particles>
    </no-ssr>
    <b-row>
      <b-col align-self="center" class="main-title">
        <div class="title-box">
          <h1>Angel Dominguez</h1>
          <h4>
            <no-ssr>
              <vue-typer
                  :text='message'
                  :repeat='Infinity'
                  :shuffle='true'
                  initial-action='typing'
                  :pre-type-delay='70'
                  :type-delay='70'
                  :pre-erase-delay='2000'
                  :erase-delay='250'
                  :erase-style='eraseStyle'
                  :erase-on-complete='true'
                  caret-animation='blink'
                  @erased='onComplete'
                >
              </vue-typer>
            </no-ssr>
          </h4>
          <hr/>
          <div class="text-center center-block">
            <br />
              <a target="_blank" href="https://github.com/angeldominguezg"><i class="fa fa-github social"></i></a>
              <a target="_blank" href="https://www.linkedin.com/in/angeldominguezg"><i class="fa fa-linkedin social"></i></a>
              <a target="_blank" href="http://instagram.com/angelddg"><i class="fa fa-instagram social"></i></a>
              <a target="_blank" href="https://twitter.com/AngelDominguezG"><i class="fa fa-twitter social"></i></a>
              <a href="mailto:angeldominguezg@gmail.com"><i class="fa fa-envelope social"></i></a>
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      message: [
        "SOFTWARE - DEVELOPER",
        "Coffee - Drinker ☕️",
        "FORWARD - THINKER"
        ],
        eraseStyle: 'select-all'
    }
  },
  methods: {
    random: function (myArray) {
      let rand = myArray[Math.floor(Math.random() * myArray.length)]
      return rand
    },
    onComplete: function() {
      return this.eraseStyle = this.random(['select-all', 'backspace', 'select-back', 'clear'])
    }
  }
}
</script>

<style>

.title-box h1 {
  font-size: 1.5rem;
  text-transform: uppercase;
  font-family: 'Anton', sans-serif;
  letter-spacing: 15px;
}

.title-box h4 {
  font-family: 'Inconsolata', monospace;
  font-weight: lighter;
  text-transform: uppercase;
  letter-spacing: 6px;
  font-size: 0.8rem;
  white-space: nowrap;
}

.main-title {
  position: fixed;
  top: 40%;
  padding-left: 50px;
  padding-right: 100px; 
}

#particles-js{
  width: 110%;
  height: 100%;
  position: fixed;
  right: 0;
  background-color: #fff;
  background-image: url('');
  background-size: cover;
  background-position: 50% 50%;
  background-repeat: no-repeat;
}

.body-particles{
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
}

.social {
  padding: 10px;
  font-size: 1.5rem;
  color: black;
}
</style>
