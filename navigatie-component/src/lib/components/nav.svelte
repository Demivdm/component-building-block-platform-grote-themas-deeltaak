<script>
  let mobileDropdownActive = false;
  let filterDropdownActive = false;
  function openMobileMenu() {
    mobileDropdownActive = !mobileDropdownActive;

    // filter dropdown sluit ook wanneer menu is gesloten
    if (!mobileDropdownActive) {
      filterDropdownActive = false;
    }
  }

  function openFilter() {
    filterDropdownActive = !filterDropdownActive;
  }
</script>

<nav>
  <section class="nav-bar" class:active={mobileDropdownActive}>
    <!-- menu is a mobile only button -->
    <button on:click={openMobileMenu}>Menu</button>
    {#if mobileDropdownActive}
      <div class="mobile-menu-dropdown">
        <button on:click={openFilter}> Filteren en zoeken</button>
        <a href="/">Inloggen</a>
        <a href="/">Werkvorm uploaden</a>
      </div>
    {/if}
    <section class="filter-dropdown" class:active={filterDropdownActive}>
      {#if filterDropdownActive}
        <section class="search-bar">
          <input type="search" />
          <button>Zoeken</button>
        </section>
        <section class="filter-menu">
          <ul class="focus">
            <button class="focus-button">Focus</button>
            <div>
              <div class="drop-down-focus">
                <li><input type="checkbox" />Ik</li>
                <li><input type="checkbox" />De ander</li>
                <li><input type="checkbox" />De wereld</li>
              </div>
            </div>
          </ul>
          <ul class="doel">
            <button class="focus-button">Doel</button>
            <div>
              <div class="drop-down-doel">
                <li><input type="checkbox" />Professioneel id ontwikkelen</li>
                <li>
                  <input type="checkbox" />Persoonlijke interesse aanspreken
                </li>
                <li><input type="checkbox" />Kennis opdoen</li>
                <li><input type="checkbox" />Richtlijnen toepassen</li>
                <li><input type="checkbox" />Golden oldies verrijken</li>
                <li><input type="checkbox" />Tools toepassen</li>
                <li><input type="checkbox" />Dialoog voeren</li>
                <li><input type="checkbox" />Praktijk betrekken</li>
              </div>
            </div>
          </ul>
          <ul class="onderwerp">
            <button class="focus-button">Onderwerp</button>
            <div>
              <div class="drop-down-onderwerp">
                <li><input type="checkbox" />Duurzaamheid</li>
                <li><input type="checkbox" />Diversiteit</li>
                <li><input type="checkbox" />Digitalisering</li>
                <li><input type="checkbox" />Democratie</li>
              </div>
            </div>
          </ul>
          <ul class="fase">
            <button class="focus-button">Fase</button>
            <div>
              <div class="drop-down-fase">
                <li><input type="checkbox" />Opwarmer</li>
                <li><input type="checkbox" />Verbreden</li>
                <li><input type="checkbox" />Verdiepen</li>
                <li><input type="checkbox" />Uitwisselen</li>
              </div>
            </div>
          </ul>
        </section>
      {/if}
    </section>
  </section>
</nav>

<style>
  * {
    overflow-x: hidden;
    color: white;
    margin: 0;
  }
  nav {
    font-size: 2em;
  }

  .nav-bar > button {
    font-size: 1em;
    width: 100vw;
    background-color: blueviolet;
    border: 0;
    padding: 1em;
  }

  .mobile-menu-dropdown {
    background-color: blueviolet;
    width: 100vw;
    display: flex;
    flex-direction: column;
  }

  .mobile-menu-dropdown *:focus {
    outline: 2px solid aqua;
    background-color: aqua;
    color: black;
  }
  .mobile-menu-dropdown * {
    display: flex;
    flex-direction: row;
    justify-content: center;
    padding: 1em;
  }

  .mobile-menu-dropdown > button {
    position: relative;
    background-color: blue;
    border: 0;
    /* transform: translateX(-50%);
    left: 45%; */
    font-size: 0.5em;
    justify-content: center;
  }

  .filter-dropdown {
    background-color: blueviolet;
  }
  /* functionaliteit voor menu */

  .filter-dropdown,
  .mobile-menu-dropdown {
    /* display: none; */
    visibility: hidden;
  }

  .nav-bar.active .mobile-menu-dropdown,
  .filter-dropdown.active {
    /* display: block; */
    visibility: visible;
  }

  @media (min-width: 700px) {
    .mobile-menu-dropdown {
      width: 100vw;
      flex-direction: row;
      justify-content: space-evenly;
    }

    .mobile-menu-dropdown > button {
      align-items: center;
      font-size: 0.7em;
    }

    .nav-bar > button {
      display: none;
    }
  }
</style>
