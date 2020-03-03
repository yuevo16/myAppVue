<template>
  <div id="app">
    <p>{{ message.value }}</p>
    <p>{{ message.value.length  }}</p>
    <p>{{ 1 + 1 }}</p>
    <ol>
      <li v-for="item in list">{{ item }}</li>
    </ol>
    <p>{{ list[2]  }}</p>
    <p>{{ list[num]  }}</p>
    <input type="text" :value="message">
    <div v-bind:text-content.prop="message">あああ</div>
    <div v-bind:scroll-top.prop="scroll">良いい</div>
    <p>{{ count }}回クリックしたよ！</p>
    <button v-on:click="increment">カウントを増やす</button>
    <input v-model="form">
    <button v-on:click="handleClick">Click</button>
    <button v-on:click="show=!show">切り替え</button>
    <transition>
      <p v-if="show">Helowwww</p>
    </transition>
    <p v-bind:class="classObject">Text</p>
    <p v-bind:style="styleObject">Text</p>
  </div>


</template>

<script>
export default {
  data: function () {
    return {
      message: {
        value: "Hello Vue!"
      },
      scroll: 0,
      list: ['りんご', 'ばなな', 'いちご'],
      num: 1,
      form: "hey!",
      show: true,
      count: 0,
      classObject: {
        child: true,
        'is-active': false
      },
      styleObject: {
        color: 'red',
        backgroundColor: 'lightgray'
      }
    }
  },
  mounted: function() {
    this.scroll = 100
  },
  methods: {
    handleClick: function(event) {
      alert(event.target)
      window.alert('テス')
    },
    increment: function() {
      this.count += 1
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
