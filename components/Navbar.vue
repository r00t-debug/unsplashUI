<template>
  <div id="navbar" class="navbar is-fixed-top is-transparent">
    <div class="navbar-brand">
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
          <div class="navbar-dropdown">
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

    let prevScrollPos = window.pageYOffset
    window.onscroll = function () {
      let currentScrollPos = window.pageYOffset
      if (prevScrollPos > currentScrollPos) {
        document.getElementById('navbar').style.top = '0'
      } else {
        document.getElementById('navbar').style.top = '-52px'
      }
      prevScrollPos = currentScrollPos
    }
  }
}

</script>

<style>
  #navbar {
    transition: top 0.3s;
    background-color: rgba(255, 255, 255, 0.5);
    backdrop-filter: blur(10px);
  }

  #nav {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
  }
  #nav-link {
    font-family: 'Montserrat', sans-serif;
  }
</style>
