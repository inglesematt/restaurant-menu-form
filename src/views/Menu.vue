<template>
  <h1>Menu</h1>

<!-- Iteration -->

  <div id="content" v-for="men in menu" :key="men.id">
      <main>
      <img :src="men.image" />
      </main>
      <section>
      <h2>{{ men.name }}</h2>
      <p>{{ men.details }}</p>
      </section>
      <aside>
      <p>£{{ men.prices.price.price }}</p>
      </aside>
 
  </div>
</template>

<script>
export default {
    data(){
        return {
           menu: null
    }
  },

// Fetched API feed

  mounted () {
    fetch('https://dev.menu.ninja/api/menu/156?key=8j5vfe%24*pfb**rzt&pretty=1')
      .then(response => response.json())
      .then(data => (this.menu = data.menu.items))
  }

}
</script>

<style>

/* Responsive Grids */

/* mobile grid */
 #content{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(100px, auto);
    grid-gap: 5px;
  max-width: 960px;
  margin: 0 auto;
  align-items: center;
  justify-items: center;
  grid-template-areas:
    "section section section section"
       "aside aside aside aside "
          "main main main main "

        }
/* desktop grid */
  @media screen and (min-width: 760px){
  #content{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(100px, auto);
  grid-gap: 10px;
  max-width: 960px;
  margin: 0 auto;
  align-items: center;
  justify-items: center;
  grid-template-areas:
 "main main section aside"

    		}
        }
		#content > *{
			padding: 10px;
		}
 
main{
    grid-area: main;
}
section{
    grid-area: section;
}
aside{
    grid-area: aside;
}

/* back-up - non-responsive */
/* #content {
  display: grid;
  grid-template-columns: 50% 30% 20%;
  grid-gap: 5px;
  max-width:960px;
  margin: 0 auto;
  align-items: center;
  justify-items: center;
}

#content div {
  padding: 20px;
} */

</style>