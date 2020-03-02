<template>
  <div id="app">
    <p>{{ message }}</p>
    <ol>
      <li v-for="item in list">{{ item }}</li>
    </ol>
    <input v-model="form">
    <button v-on:click="handleClick">Click</button>
    <button v-on:click="show=!show">切り替え</button>
    <transition>
      <p v-if="show">Helowwww</p>
    </transition>
  </div>


</template>

<script>
export default {
  data: function () {
    return {
      message: "Hello Vue!",
      list: ['りんご', 'ばなな', 'いちご'],
      form: "hey!",
      show: true
    }
  },
  methods: {
    handleClick: function(event) {
      alert(event.target)
      window.alert('テス')
    }
  }
}
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}

.v-enter-active, .v-leave-active {
  transition: opacity 1s;
}

.v-enter, .v-leave-to {
  opacity: 0;
}
</style>
