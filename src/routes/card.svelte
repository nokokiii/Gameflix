<script>
  let hovering = false;
  function enter() {
    hovering = true;
  }

  function leave() {
    hovering = false;
  }
</script>

<div class="card" on:mouseenter={enter} on:mouseleave={leave} >
  <img src="/background_cs.jpg" alt="" />
  <!-- your html code goes here -->
  {#if hovering}
    <div class="info">
      <span>Title</span>
      <button>See more</button>
    </div>
  {/if}
</div>

<style>
  /* // your css code goes here */

  /* wygląd karty */

  .card {
    position: relative;
    width: 284px;
    height: 150px;
    background: none;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  }

  .card > img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .card > .info {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 5px;
  }

  .card > .info > span {
    color: white;
    font-size: 20px;
    margin-left: 15px;
    margin-bottom: 10px;
  }

  .card > .info > button {
    background: none;
    border: none;
    color: white;
    font-size: 20px;
    margin-right: 15px;
    margin-bottom: 10px;
    cursor: pointer;
  }

  .card > .info > button:hover {
    color: #ff0000;
  }
</style>
