<script>
export default {
  name: 'Card',
  props: [
    'category',
    'mission'
  ],
  data() {
    return {
      rotate: 'rotateY(0deg)'
    }
  },
  computed: {
    computedRotate() {
      return this.rotate;
    }
  },
  methods: {
    rotateMethod() {
      if (this.rotate == 'rotateY(180deg)')
        this.rotate = 'rotateY(0deg)'
      else
        this.rotate = 'rotateY(180deg)'
    }
  },  
}

</script>

<template>
  <div class="card" v-on:click="rotateMethod()" v-bind:style="{transform: computedRotate}">
    <div class="front">
        <p class="category">{{category}}</p>
    </div>
    <div class="back">
        <p class="mission">{{mission}}</p>
    </div>
  </div>
</template>

<style>
/* $color-card: #8EB8E5; */

.card { 
  width: 12rem;
  height: 12rem;
  font-size: 1.2rem;
  margin: 1em 0;

  transform-style: preserve-3d;
  transition: .5s;
  position: relative;
  cursor: pointer;
}

.front {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    padding: .75em;
    font-size: 1.25em;

    display: flex;
    justify-content: center;
    align-items: center;

    background: #8EB8E5;
    border: 2px solid #526d89;
    border-radius: 1rem;

    backface-visibility: hidden;
    overflow: hidden;
}

.card:nth-child(2) .front, 
.card:nth-child(5) .front
{background: #BB8588; border: 2px solid #946063;}

.card:nth-child(2) .back,
.card:nth-child(5) .back
{background: #d4a2a5; border: 2px solid #BB8588;}

.card:nth-child(3) .front,
.card:nth-child(8) .front,
.card:nth-child(12) .front
{background: #A3C4BC; border: 2px solid #72928a;}

.card:nth-child(3) .back,
.card:nth-child(8) .back,
.card:nth-child(12) .back
{background: #b8c9c5; border: 2px solid #A3C4BC;}

.card:nth-child(4) .front, 
.card:nth-child(9) .front,
.card:nth-child(11) .front
{background: #A88FAC; border: 2px solid #8c6c91;}

.card:nth-child(4) .back, 
.card:nth-child(9) .back,
.card:nth-child(11) .back
{background: #cab4ce; border: 2px solid #A88FAC;}


.back {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: .75em;

  display: flex;
  justify-content: center;
  align-items: center;

  background: #7C99B4;
  border: 2px solid #566a7c;
  border-radius: 1rem;

  backface-visibility: hidden;
  overflow: hidden;
  transform: rotateY(180deg);
}
</style>
