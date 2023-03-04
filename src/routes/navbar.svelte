<script>
  import { slide } from "svelte/transition";

  let showItems = false;
  let isSearchbar = false;
  let i = 3;
  let items = ["profile", "settings", "Sign In"];

  function showProfileOptions() {
    if (showItems == true) {
      showItems = false;
    } else {
      showItems = true;
    }
  }

  function showSearchbar() {
    if (isSearchbar == true) {
      isSearchbar = false;
    } else {
      isSearchbar = true;
    }
  }
</script>

<!-- Stworzenie oddzielnych plików na componenty takie jak search, profile etc. -->

<nav>
  <div class="logo">
    <img src="" alt="Logo" />
  </div>

  <div class="subpages">
    <a href=".">Main Page</a>
    <a href=".">Popular</a>
    <a href=".">Adventure games</a>
    <a href=".">FPS games</a>
    <a href=".">RPG games</a>
    <a href=".">Strategy games</a>
    <a href=".">Sport games</a>
  </div>

  <div class="nav-options">
    <!-- search -->
    <div class="search">
      <button on:click={showSearchbar}>
        <img src="/search.png"/> <!-- Nie dopisywać alt. Aby nie psuć wyglądu wrazie nie wczytania się ikony -->
      </button>
      {#if isSearchbar}
        <div class="searchbar" transition:slide|local>
          <input type="text" placeholder="Search..." />
        </div>
      {/if}
    </div>
    <!-- Notifications -->
    <!-- pokliknięciu pojawiają się notyfikacje (np. odpiwedzi na komentrze etc.) -->
    <div class="notifications">
      <button>
        <img src="/notifications.png" />
      </button>
    </div>
    <!-- profile -->
    <!-- Dopracować szerokość listy i żeby w liście były buttony/a. -->
    <div class="profile">
      <button on:click={showProfileOptions}>
        <img src="" alt="Profile" />
      </button>
      {#if showItems}
        {#each items.slice(0, i) as item}
          <div class="profile-options" transition:slide|local>
            <a href="." >{item}</a>
          </div>
        {/each}
      {/if}
    </div>
  </div>
</nav>

<style>
  nav {
    width: 100vw;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    position: fixed;
    align-items: center;
    top: 0;
    z-index: 2;
  }

  div.nav-options {
    display: flex;
    flex-direction: row;
  }

  div.nav-options > div.search {
    display: flex;
    flex-direction: row;
  }

  div.profile {
    width: 200px;
  }

  div.profile > button {
    width: 100%;
  }

  div.profile-options {
    box-sizing: border-box;
    width: 100%;
    padding: 10px;
    border: 1px solid #eee;
  }
</style>
