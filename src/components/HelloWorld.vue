<template>
  <div class="container">
    <div class="item-a formats title-box">
      <p class="title">Type key to hear character speak!</p>
    </div>
    <div class="item-b formats inner-grid">
      <div>
        <img src="../../static/c3po.png" style="height: 20em;">
      </div>
      <div>
        <img src="../../static/darthv.png" style="height: 20em;">
      </div>
      <div>
        <img src="../../static/stormtrooper.png" style="height: 20em;">
      </div>
      <div>
        <button id="C3PO" class="button" @click="characters('67')">C</button>
      </div>
      <div>
        <button id="Darth" class="button" @click="characters('68')">D</button>
      </div>
      <div>
        <button id="Storm" class="button" @click="characters('83')">S</button>
      </div>
    </div>
    <div class="item-c"><p class="insta">INSTAGRAM: @charlottejewer</p></div>
  </div>
</template>

<script>
export default {

  created: function () {
    window.addEventListener('keyup', this.characters, event)
  },
  methods: {
    characters: function (event) {
      console.log(event)
      var c3po = new Audio('../../static/c3po.mp3')
      var darth = new Audio('../../static/swvader02.mp3')
      var storm = new Audio('../../static/Stormtrooper.mp3')

      console.log('in a function')
      console.log('Letter id is: ', event.keyCode)
      if (event.keyCode === 67 || event === '67') {
        c3po.play()
        document.getElementById('C3PO').style.backgroundColor = 'gold'
        document.getElementById('C3PO').style.color = 'black'
        document.getElementById('Darth').style.backgroundColor = 'black'
        document.getElementById('Storm').style.backgroundColor = 'black'
        document.getElementById('Darth').style.color = 'gold'
        document.getElementById('Storm').style.color = 'gold'
      } else if (event.keyCode === 68 || event === '68') {
        darth.play()
        document.getElementById('Darth').style.backgroundColor = 'gold'
        document.getElementById('Darth').style.color = 'black'
        document.getElementById('C3PO').style.backgroundColor = 'black'
        document.getElementById('C3PO').style.color = 'gold'
        document.getElementById('Storm').style.backgroundColor = 'black'
        document.getElementById('Storm').style.color = 'gold'
      } else if (event.keyCode === 83 || event === '83') {
        storm.play()
        document.getElementById('Storm').style.backgroundColor = 'gold'
        document.getElementById('Storm').style.color = 'black'
        document.getElementById('C3PO').style.backgroundColor = 'black'
        document.getElementById('C3PO').style.color = 'gold'
        document.getElementById('Darth').style.backgroundColor = 'black'
        document.getElementById('Darth').style.color = 'gold'
      } else {
        document.getElementById('Storm').style.backgroundColor = 'black'
        document.getElementById('Storm').style.color = 'gold'
        document.getElementById('C3PO').style.backgroundColor = 'black'
        document.getElementById('C3PO').style.color = 'gold'
        document.getElementById('Darth').style.backgroundColor = 'black'
        document.getElementById('Darth').style.color = 'gold'
      }
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 10% auto 10%;
  grid-template-rows: 1fr 2fr 0.5fr;
  background-color: transparent;
  grid-template-areas:
  ". header ."
  ". main ."
  "footer footer footer"
}
.formats {
  color: white;
  margin: auto;
}
.item-a {
  grid-area: header;
}
.item-b {
  grid-area: main;
}
.item-c {
  grid-area: footer;
  align-self: end;
  color: gold;
}
.title-box {
  border-radius: 1em;
  border: 2px solid gold;
  background-color: black;
  color: gold;
  width: 35em;
  height: 6em;
  padding-top: 1em;
  margin-left: auto;
  margin-right: auto;
}
.title {
  font-size: 150%;
}
.inner-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 3fr 1fr;
  height: 100%;
  width: 100%;
}
.inner-grid > div {
  color: white;
}
.button {
    background-color: black;
    border: 2px solid gold;
    color: gold;
    padding: 16px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    transition: opacity 4s;
    cursor: pointer;
    border-radius: 4px;
}
.button:hover {
  color: black;
  background-color: gold;
}
.insta {
  border-radius: 1em;
  border: 2px solid gold;
  background-color: black;
  color: gold;
  width: 16em;
  height: 2em;
  padding-top: 0.6em;
  margin-left: auto;
  margin-right: auto;
}
</style>
