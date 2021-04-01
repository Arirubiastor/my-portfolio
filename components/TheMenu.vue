<template>
<div class="page__container d-flex flex-column">
  <div class="nav__container d-flex flex-column justify-content-center">

    <!-- <div class="nav-item__container mx-4 pl-1 pr-1 py-3">
      <nuxt-link to="/artwork">artwork</nuxt-link>
      <div>
        <img
          src="~assets/icons/next-128px.png"
          alt="A black arrow pointing to the right"
          class="nav-item__icon"
        />
      </div>
    </div> -->
    <nuxt-link to="/artwork">
      <div class="nav-item__container mx-4 pl-1 pr-1 py-3">
        artwork
        <div>
          <img
            src="~assets/icons/next-128px.png"
            alt="A black arrow pointing to the right"
            class="nav-item__icon"
          />
        </div>
      </div>
    </nuxt-link>

    <nuxt-link to="/github-repositories">
      <div class="nav-item__container mx-4 pl-1 py-3">
        repositories
        <div>
          <img
            src="~assets/icons/next-128px.png"
            alt="A black arrow pointing to the right"
            class="nav-item__icon"
          />
        </div>
      </div>
    </nuxt-link>

    <nuxt-link to="/digital-products">
      <div class="nav-item__container mx-4 pl-1 py-3">
        projects
        <div>
          <img
            src="~assets/icons/next-128px.png"
            alt="A black arrow pointing to the right"
            class="nav-item__icon"
          />
        </div>
      </div>
    </nuxt-link>
    
    <nuxt-link to="/blog">
      <div class="nav-item-bottom__container mx-4 pl-1 py-3">
        blog
        <div>
          <img
            src="~assets/icons/next-128px.png"
            alt="A black arrow pointing to the right"
            class="nav-item__icon"
          />
        </div>
      </div>
    </nuxt-link>

  </div>
    <div class="marquee__menu mt-auto">
      <ul class="marquee__content">
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>

        <!--  Repeated marquee items -->
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
        <li class="marquee__item">
          &nbsp;{{ sectionTitle1 }} &bull; {{ sectionTitle2 }} &bull;
        </li>
      </ul>
    </div>
</div>
  
</template>

<script>
export default {
  data() {
    return {
      sectionTitle1: "Visual Artist",
      sectionTitle2: "Frontend Developer",
    };
  },
};
</script>

<style lang="scss">
$text-global-color: #343a40; // gray-800

.page__container {
  height: calc(100vh - 64px);
}

.nav__container {
  height: 100%;
}

.nav-item__container {
  font-size: 1.9rem;
  border-bottom: 3px solid $text-global-color;
  font-weight: 500;
  display: flex;
  justify-content: space-between;
}

.nav-item-bottom__container {
  font-size: 1.9rem;
  color: $text-global-color;
  font-weight: 500;
  display: flex;
  justify-content: space-between;
}

.nav-item__icon {
  width: 1.4rem;
}

.marquee__menu {
  width: 100vw;
  height: 27px;
  border-top: 2px solid $text-global-color;
  border-bottom: 2px solid $text-global-color;
  overflow: hidden;

  .marquee__content {
    display: flex;
    list-style: none;
    animation: scrolling 4s linear infinite;

    .marquee__item {
      font-size: 1rem;
      text-transform: uppercase;
      /*   height: 30px;
      width: 60px; */
      flex-shrink: 0;
    }
  }

  @keyframes scrolling {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
}

// Small sm
@media (min-width: 576px) {
  .nav-item__container {
    font-size: 4rem;
    border-bottom: 3px solid $text-global-color;
  }

  .nav-item-bottom__container {
    font-size: 4rem;
  }

  .nav-item__icon {
    width: 3.2rem;
  }

  .marquee__content {
    animation: scrolling 10s linear infinite !important;
  }

  @keyframes scrolling {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
}

// Medium md
@media (min-width: 768px) {
  .page__container {
    height: calc(100vh - 64px);
  }
  .nav-item__container {
    font-size: 4.5rem;
    border-bottom: 3px solid $text-global-color;
  }

  .nav-item-bottom__container {
    font-size: 4.5rem;
  }

  .nav-item__icon {
    width: 4rem;
  }

  .marquee__menu {
  height: 35px;
  .marquee__content {
    .marquee__item {
      font-size: 1.3rem;
    }
  }
  }
}

// Large lg
@media (min-width: 992px) {
  .nav-item__container {
    font-size: 4.5rem;
    border-bottom: 3px solid $text-global-color;
  }

  .nav-item-bottom__container {
    font-size: 4.5rem;
  }

  .nav-item__icon {
    width: 4rem;
  }

  .marquee__content {
    animation: scrolling 15s linear infinite !important;
  }

  @keyframes scrolling {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
}
// Extra large lx
@media (min-width: 1200px) {
  .nav-item__container {
    font-size: 7rem;
    border-bottom: 3px solid $text-global-color;
  }

  .nav-item-bottom__container {
    font-size: 7rem;
  }

  .nav-item__icon {
    width: 5.5rem;
  }
}
</style>