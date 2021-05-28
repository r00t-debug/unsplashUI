<template>
  <div id="navbar" class="navbar is-fixed-top is-transparent transluscent">
    <div class="navbar-brand">
      <div id="navbar-spacer" />
      <nuxt-link class="navbar-item" to="/">
        <h1 id="nav" class="title is-4">
          Image Gallery
        </h1>
      </nuxt-link>
      <a role="button" class="navbar-burger" data-target="navMenu" aria-label="menu" aria-expanded="false">
        <span aria-hidden="true" />
        <span aria-hidden="true" />
        <span aria-hidden="true" />
      </a>
    </div>
    <div id="navMenu" class="navbar-menu">
      <div class="navbar-end">
        <nuxt-link id="nav" class="navbar-item" to="/">
          Home
        </nuxt-link>
        <nuxt-link id="nav" class="navbar-item" to="/pictures">
          Gallery
        </nuxt-link>
        <div class="navbar-item has-dropdown is-hoverable">
          <nuxt-link id="nav" class="navbar-link" to="">
            Contact
          </nuxt-link>
          <div id="dropdown" class="navbar-dropdown is-boxed">
            <a id="contact" target="_blank" href="https://github.com/imaginaries" class="navbar-item">
              Github
            </a>
            <a id="contact" target="_blank" href="https://www.instagram.com/swattyyt/" class="navbar-item">
              Instagram
            </a>
            <a id="contact" target="_blank" href="https://www.youtube.com/channel/UCn0jbqLLQtmUvbJ89K6BUdA" class="navbar-item">
              Youtube
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  mounted () {
    document.addEventListener('DOMContentLoaded', () => {
      // Get all "navbar-burger" elements
      const $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0)
      // Check if there are any navbar burgers
      if ($navbarBurgers.length > 0) {
      // Add a click event on each of them
        $navbarBurgers.forEach((el) => {
          el.addEventListener('click', () => {
          // Get the target from the "data-target" attribute
            const target = el.dataset.target
            const $target = document.getElementById(target)

            // Toggle the "is-active" class on both the "navbar-burger" and the "navbar-menu"
            el.classList.toggle('is-active')
            $target.classList.toggle('is-active')
          })
        })
      }
    })
  }
}
</script>

<style>
  /* global class */
  .transluscent {
    content: '';
    background-color: rgba(240, 240, 240, 0.7);
    backdrop-filter: saturate(180%) blur(20px);
  }

  .navbar-brand .navbar-item, a.navbar-item {
    transition: all 0.3s ease 0s;
  }
  .navbar-brand .navbar-item:hover {
    filter: opacity(75%);
  }

  #navbar {
    transition: top 0.3s;
    padding: 0 3vw;
  }

  #navbar-spacer {
    display: none;
    width: 3.25rem;
  }

  #nav {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
  }
  #nav-link {
    font-family: 'Montserrat', sans-serif;
  }

  @media screen and (min-width: 1024px) {
    .navbar.is-transparent .navbar-dropdown a.navbar-item:focus, .navbar.is-transparent .navbar-dropdown a.navbar-item:hover {
    color: #3273dc;
    }

    #dropdown {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      padding: 8px;
      top: calc(100% + (0px));
      left: -14px;
    }

    #dropdown a.navbar-item {
      padding: 0.375rem 1.5rem;
    }
  }

  .navbar-burger {
    margin-left: 0;
  }

  .navbar-burger:hover {
    background-color: transparent;
  }

  @media screen and (max-width: 1023px) {
  #navbar-spacer {
    display: block;
  }

  .navbar {
    display: flex;
    flex-wrap: wrap;
  }
  .navbar-brand {
    min-width: 100%;
    justify-content: space-between;
  }
  .navbar-menu {
    margin-left: auto;
    min-width: 50%;
  }
}
</style>
