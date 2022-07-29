<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->

<script>
export default {
  data() {
    return {
      color: '#d7cbca',
    }
  },
  methods: {
    generateColor() {
      this.color = '#' + Math.floor(Math.random()*16777215).toString(16);
    }
  },
  setup() {
    this.generateColor();
  }
}
</script>

<template>
  <div class="wrapper" :style="{'background-color' : color}">
    <div class="content">
      <button @click.prevent="generateColor">Generate New Random Color</button>
  	<p>{{color}}</p>
    </div>
	</div>
</template>

<style scoped>
.wrapper {
  padding: 1rem;
  align-items: center;
  justify-content: center;
  min-height: 200px;
  display: flex;
}
  
  .content {
    background-color: #fff;
    padding: 1rem;
    border-radius: 10px;
  }
</style>
