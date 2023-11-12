<script>
  import { onMount } from "svelte";

  let diyaLink,fireworkLink;
    onMount(()=>{
        let num = Math.floor(Math.random()*100);
        console.log(num)
        if( num < 50 ){
            diyaLink.click();
        }else{
            fireworkLink.click();
        }

    })
</script>

<main style="opacity: 0%;">
<a href="/diya" bind:this="{diyaLink}">diya</a>
<a href="/fireworks" bind:this="{fireworkLink}">fireworks</a>
</main>

<style>

</style>

