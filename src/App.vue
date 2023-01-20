<script>
export default {
  data: ()=> {
    return {
      hearts: 5,
      enemyHearts: 4,
      playerDeath: false,
      enemyDeath: false,
      enemySave: false,
      friendship: true,
    }
  },
  methods: 
  {
    Attack()
    {
      this.friendship == false;
      this.hearts--; 
      this.enemyHearts--;
      console.log(this.hearts);
       if(this.hearts == 0)
       {
         this.playerDeath = true;
      }
      if(this.enemyHearts == 0)
      {
        this.enemyDeath = true;
      }
    },
    Interact()
    {
      this.hearts--;
      if(this.enemyHearts == 1)
      {
        this.enemySave = true;
      }
      if(this.hearts == 0)
      {
        this.playerDeath = true;
      }
    },

  }
}
</script>


<template>
  <header>   
          <button v-on:click.prevent="Attack">Attack</button>
          <button v-on:click.prevent="Interact">Interact</button>

          <div v-if="playerDeath">YOU HAVE DIED</div>
          <div v-if="enemySave">YOU SPARE HIS LIFE</div>
          <div v-if="playerDeath || enemySave">Play again?</div> 
          <div v-if="enemyDeath">YOU HAVE KILLED</div>
          
    <ul>
      <li v-for="n in hearts" :key="n">
        <img class="logo" src=https://freesvg.org/img/1646656079PixelArt-Heart-1.png visibility = "visible" width="25" height="25" />
      </li>
    </ul>

    <div class="Images" id= "knight">
      <img alt="Knight Img" class="logo" src=https://openclipart.org/image/400px/164017 visibility = "visible" width="125" height="125" />
    </div>


    <ul>
      <li v-for="n in enemyHearts" :key="n">
        <img class="logo" src=https://freesvg.org/img/1646656079PixelArt-Heart-1.png visibility = "visible" width="25" height="25" />
      </li>
    </ul>


    <div class="Images" id= "wizard">
      <img alt="Wizard Img" class="logo" src=https://freesvg.org/img/maghetto-.png visibility = "visible" width="125" height="125" />    
    </div>



  </header>

  <main>
  </main>
</template>

<style>
@import './assets/base.css';


#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}
button{
  padding: 5px;
}
header {
  line-height: 1.5;
}

li {
  display: inline-block;
  list-style-type : '';
  
}




.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: rgb(0, 0, 0);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
body {
  width: 500px;
  height: 1400px;
  margin: 0 auto;
  background: rgb(221, 221, 167);
}
.Images {
  display: inline-block;
  color: white;
}

#knight {
  position: relative;
  top: 50px;
  left: 0;
}

#wizard{
  position: relative;
  top: 50px;
  left: 0;
}

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
