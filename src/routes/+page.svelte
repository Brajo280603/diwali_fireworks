<script>

    
    import { Fireworks } from '@fireworks-js/svelte'
  import { onMount } from 'svelte';

    let diyaImg ;

    onMount(()=>{
        diyaImg.src = "/diya_unlit.jpg"
        
        document.querySelector(".glow").classList.remove("lightupGlow");
        document.querySelector(".flame").classList.remove("lightupFlame");

        document.querySelector(".flame").classList.remove("defaultFlameAnim");
    })

    function lightUp(){
        document.querySelector(".glow").classList.add("lightupGlow");
        document.querySelector(".flame").classList.add("lightupFlame");
        document.querySelector(".diwali_text").innerText = "Happy Diwali"
        // diyaImg.src = "/diya_lit.jpg"    
        setTimeout(()=>{
            document.querySelector(".flame").classList.remove("lightupFlame");
            document.querySelector(".flame").classList.add("defaultFlameAnim");
            document.querySelector(".glow").style.opacity = "100%";

        },1000)
    }
    
    

</script>

<main>

    <div class="diya">
       <p class="diwali_text">Light Up</p>

    <img bind:this="{diyaImg}"  id="diya-img" alt=""  on:click="{lightUp}"> 
    
    <div class="holder">
          <div class="oil_lamp">
            <div class="thread" on:click={lightUp} ></div>
            
                <div class="glow lightupGlow"></div>
                <div class="flame lightupFlame defaultFlameAnim"></div>
            
            
          </div>
        </div>
   </div>

</main>

<style>


  @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');


  .diwali_text{
    color:transparent;
    font-family: 'Great Vibes', cursive;
    z-index: 100;
    position: absolute;
    top:27%;
    font-size: 3rem;
    animation: Animation 5s ease infinite reverse;
    background: linear-gradient(130deg, #ff7e00, #ffffff, #fbff00);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip : text;

  }
  

    .diya{
        /* height:100%; */
        /* max-width:100%; */
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
    }

    main{
        margin:0;
        padding: 0;
        
    }




    #diya-img{
        /* width:100%; */
        /* position: absolute; */
        /* top: -25%; */
        /* translate: -50% 50%; */
        /* left: 25%; */
        /* translate: 50% 50%; */
        box-shadow: 0 0 200px rgba(0,0,0,0.9) inset;
        /* z-index: -100; */
    }

*, *:before, *:after {
	margin: 0;
	padding: 0;
	word-break: break-all;
  box-sizing: border-box;
  scroll-behavior: smooth;
}







img {
	border: 0;
}





.holder {

  /* margin-top:15rem; */
  background-color: transparent;
/*   margin: 12rem 12rem 1rem 0; */
  width: 150px;
  height: 40px;
  position: absolute;
  /* top: 23%; */
  /* left: 47.5%; */

  /* top:0;
  left:0;
  right:0;
  bottom:0; */

top:64.8%;
left:50%;

}

.holder *, .holder *:before, .holder *:after {
  position: absolute;
  content: "";
}





.thread {  
  width: 10px;
  height: 36px;
  top: -17px;
  left: 50%;
  z-index: 1;
  border-radius: 40% 40% 0 0;
  transform: translateX(-50%);
  /* background: #121212; */
  background: transparent;
  background: -moz-linear-gradient(#d6994a, #4b232c, #121212, black, #e8bb31 90%);
  background: -webkit-linear-gradient(#d6994a, #4b232c, #121212, black, #e8bb31 90%);
  background: -o-linear-gradient(#d6994a, #4b232c, #121212, black, #e8bb31 90%);
  background: -ms-linear-gradient(#d6994a, #4b232c, #121212, black, #e8bb31 90%);
  background: linear-gradient(#d6994a, #4b232c, #121212, black, #e8bb31 90%);
}

.flame {
  width: 24px;
  /* height: 120px; */
  left: 50%;
  transform-origin: 50% 100%;
  transform: translateX(-50%);
  bottom: 100%;
  border-radius: 50% 50% 20% 20%;
  background: rgba(255, 255, 255, 1);
  background: -moz-linear-gradient(white 80%, transparent);
  background: -webkit-linear-gradient(white 80%, transparent);
  background: -o-linear-gradient(white 80%, transparent);
  background: -ms-linear-gradient(white 80%, transparent);
  background: linear-gradient(white 80%, transparent);
}
/*  */
.flame:before {
  width: 100%;
  height: 100%;
  border-radius: 50% 50% 20% 20%;
  box-shadow: 0 0 15px 0 rgba(247, 93, 0, .4), 0 -6px 4px 0 rgba(247, 128, 0, .7);
}

@keyframes moveFlame {
  0%, 100% {
    transform: translateX(-50%) rotate(-2deg);
  }
  50% {
    transform: translateX(-50%) rotate(2deg);
  }
}

@keyframes enlargeFlame {
  0%, 100% {
    height: 120px;
  }
  50% {
    height: 140px;
  }
}

@keyframes lightupFlame {
    0%{
        height: 0px;
        width:0px;
    }
    10%{
        height:10px;
        width:70px;
    }
    100%{
        height:120px;
    }
}

@keyframes lightupGlow {
    0%{
        opacity: 0%;
    }
    50%{
        opacity: 0%;
    }
    90%{
      opacity: 100%;  
    }
    100%{
        opacity: 100%;
    }
}

@keyframes Animation { 
    0%{background-position:10% 0%}
    50%{background-position:91% 100%}
    100%{background-position:10% 0%}
}

.lightupFlame{
    animation: lightupFlame 1s  forwards;
}

.lightupGlow{
    animation: lightupGlow 1s  ;
    animation-fill-mode: forwards;
}

.defaultFlameAnim{
    animation: moveFlame 6s linear infinite, enlargeFlame 5s linear infinite;
}



.glow {
    opacity: 0%;
  width: 26px;
  height: 60px;
  border-radius: 50% 50% 35% 35%;
  left: 50%;
  top: -48px;
  transform: translateX(-50%);
  background: rgba(0, 133, 255, .7);
  box-shadow: 0 -40px 30px 0 #dc8a0c, 0 40px 50px 0 #dc8a0c, inset 3px 0 2px 0 rgba(0, 133, 255, .6), inset -3px 0 2px 0 rgba(0, 133, 255, .6);
  
}

.glow:before {
  width: 70%;
  height: 60%;
  left: 50%;
  transform: translateX(-50%);
  bottom: 0;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.35);
}



@keyframes blinkIt {
  50% { opacity: .8;}
}


</style>