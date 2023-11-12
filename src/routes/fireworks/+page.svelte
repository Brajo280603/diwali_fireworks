<script>
 import { Fireworks } from '@fireworks-js/svelte'
  import { onMount } from 'svelte';
  

  let enabled = false
  let options = {
    opacity: 0.5,
    sound:{
        enabled:true,
        volume:{
            min:4,
            max:10
        },
    
    }
  }

  

  function start(){
    enabled = !enabled;
    document.querySelector(".rocket").style.display = "none";
    document.querySelector(".btn").style.fontSize = "3rem";
  }
</script>

<main>
<div class="fireworks">
    <div class="btn">
        {enabled ? 'Happy Diwali' : 'Like fireworks in the sky, may this Diwali bring dazzling moments that light up your world with delight.'}
    </div>

      <img src="/rocket.png" alt="" class="rocket" on:click={start}>

      {#if enabled}
        <Fireworks {options} class="fireworks " />
      {/if}
</div>
</main>

<style>

@import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');

  :global(.fireworks) {
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    position: fixed;
    background: #000;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .btn {


   
     
       padding:1rem;
    
    

    color:transparent;
    /* color:white; */
    font-family: 'Great Vibes', cursive;
    z-index: 100;
    
    
    font-size: 2rem;
    animation: Animation 5s ease infinite reverse;
    background: linear-gradient(130deg, #ff7e00, white, #fbff00);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip : text;
    /* border:2px solid white; */
    /* border-radius: 1rem; */
    border:none;
    cursor: pointer;
  }


@keyframes Animation { 
    0%{background-position:10% 0%}
    50%{background-position:91% 100%}
    100%{background-position:10% 0%}
}

.rocket{
    position: absolute;
    width:10rem;
    bottom:5%;
    left:50%;
    translate: -50% -50%; 
    cursor: pointer;
animation: shake 1s infinite;
}


@keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
}

</style>