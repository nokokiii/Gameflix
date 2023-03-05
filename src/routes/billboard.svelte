<script>
  import FaPlay from 'svelte-icons/fa/FaPlay.svelte'
  import FaInfoCircle from 'svelte-icons/fa/FaInfoCircle.svelte'
</script>

<div class="billboard">
  <h1>proponowana gra</h1>
  <button class="play"><div class="icon">
    <FaPlay />
  </div>Zagraj</button>
  <button class="info">
    <div class="icon">
      <FaInfoCircle />
    </div>Więcej informacji</button>
  
</div>

<style>
  h1 {
    color: red;
  }

  /* guzik zagraj */
  .play {
    background-color: #ffffff;
    border: none;
    color: black;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 5px;
  }

  .play:hover {
    background-color: #f1f1f194;
  }

/* guzik więcej informacji */
  .info {
    background-color: #c4c4c4;
    border: none;
    color: black;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 5px;
    border-radius: 5px;
    align-items: center;
    justify-content: center;
  }

  .info:hover {
    background-color: #888888;
  }

/* ikonki */
  .icon{
    display: inline-block;
    width: 20px;
    height: 20px;
    margin-right: 10px;
  }

 /*tło*/
  .billboard {
    width: 100%;
    height: 90vh;
    background-color: #f1f1f1;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
</style>
