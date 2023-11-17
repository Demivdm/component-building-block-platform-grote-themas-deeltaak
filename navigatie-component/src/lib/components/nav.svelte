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
  nav {
    font-size: 2em;
  }

  .nav-bar > button {
    font-size: 1em;
    width: 100vw;
    background-color: blueviolet;
    border: 0;
  }

  .mobile-menu-dropdown * {
    display: flex;
    flex-direction: row;
  }
  /* functionaliteit voor menu */

  .filter-dropdown,
  .mobile-menu-dropdown {
    display: none;
  }

  .nav-bar.active .mobile-menu-dropdown,
  .filter-dropdown.active {
    display: block;
  }
</style>
