<template>
  <b-container class="bv-example-row bv-example-row-flex-cols">
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
    <b-row>
      <b-col align-self="center" class="main-title">
        <div class="title-box">
          <h1>Angel Dominguez</h1>
          <h4>
            <vue-typer
                :text='message'
                :repeat='Infinity'
                :shuffle='true'
                initial-action='typing'
                :pre-type-delay='70'
                :type-delay='70'
                :pre-erase-delay='2000'
                :erase-delay='250'
                erase-style='select-back'
                :erase-on-complete='true'
                caret-animation='blink'
                @erased='onComplete'
              >
            </vue-typer>
          </h4>
          <hr>
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
        "Testing, testing... 1 2 3 ",
        "Ok! i hope everything works fine  ;)",
        "Ummm, Hello World!",
        "Just in case haha"
        ]
    }
  },
  methods: {
    onComplete: function() {
      // handle event when VueTyper has finished all typing/erasing
      this.message = 'bye'
    }
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css?family=Anton|Inconsolata');

.title-box h1 {
  text-transform: uppercase;
  font-family: 'Anton', sans-serif;
}
.title-box h4 {
  font-family: 'Inconsolata', monospace;
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
</style>
