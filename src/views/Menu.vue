<template>
  <h1>Menu</h1>
  <div v-for="men in menu" :key="men.id">
      <h2>{{ men.name }}</h2>
      <p>£{{ men.prices.price.price }}</p>
            <p>{{ men.details }}</p>
      <img :src="men.image" />
  </div>
</template>

<script>
export default {
    data(){
        return {
           menu: null
    }
  },
  mounted () {
    fetch('https://dev.menu.ninja/api/menu/156?key=8j5vfe%24*pfb**rzt&pretty=1')
      .then(response => response.json())
      .then(data => (this.menu = data.menu.items))
  }

}
</script>

<style>

</style>