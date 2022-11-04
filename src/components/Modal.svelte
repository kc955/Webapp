<!-- if you're not using typescript, remove lang="ts" attribute from the script tag -->
<script lang="ts">
    import { Button } from "attractions";

    let isOpen = false
    function open() {
      isOpen = true
    }
    function close() {
      isOpen = false
    }
    export let title;
    export let link;
  </script>

<style>
  div.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
  }
  div.backdrop {
    position: absolute;
    width: 80%;
    height: 70%;
    background-color: rgba(0, 0, 0, 0.4);

    justify-content: center;
    align-items: center;
  }
  div.content-wrapper {
    z-index: 10;
    width: 60%;
    height: 60%;
    border-radius: 0.3rem;
    background-color: white;
    overflow: hidden;
  }
  div.content {
    overflow: auto;
    width: 100%;
    height: 100%;
  }
</style>

<div>
    <Button on:click={open} style="font-size: 1vw;">Read More</Button>

    {#if isOpen}
    <div class="modal">
        <div class="backdrop" on:click={close} />
          <Button on:click={close} style="font-size: 3vw; color:black">x</Button>
          <div class="content-wrapper">
            <div>
                <h1>{title}</h1>
            </div>
            <div class="content">
              <iframe src={link} style="width:100%; height:100%;"></iframe>
          </div>
        </div>
    </div>
    {/if}
</div>  
