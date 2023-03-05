<script>
	import { fade,slide } from 'svelte/transition';

	let showItems = false;
    let isSearchbar = false;
	let items = ['profile', 'settings', 'Sign In'];
    let itemsLen = items.length

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

<style>
    nav {   
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        position: fixed;
        top: 0;
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
        width: 200px
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

<!-- Stworzenie oddzielnych plików na componenty takie jak search, profile etc. -->

<nav>
    <div>
        <img src="" alt="Logo">
    </div>

    <div>
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
        <!-- Pojawia się input(text), ale pojawia się podspodem. Do naprawienia i ostylizownia -->
        <div class="search">
            <button on:click={showSearchbar}>
                <img src="" alt="Search">
            </button>
            {#if isSearchbar}
            <div class="searchbar" transition:fade|local>
                <input type="text" placeholder="Search...">
            </div>
            {/if}
        </div>
        <!-- Notifications -->
        <!-- pokliknięciu pojawiają się notyfikacje (np. odpiwedzi na komentrze etc.) -->
        <div>
            <button>
                <img src="" alt="Notifications">
            </button>
        </div>
            <!-- profile -->
        <!-- Dopracować szerokość listy i żeby w liście były buttony/a. -->
        <div class="profile">
            <button on:click={showProfileOptions}>
                <img src="" alt="Profile">
            </button>
            {#if showItems}
            {#each items.slice(0, itemsLen) as item}
            <div class="profile-options" transition:slide|local>
                {item}
            </div>
            {/each}
            {/if}
        </div>
            
    </div>
</nav>