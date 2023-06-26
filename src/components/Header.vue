<script>

export default {

  data() {
    return {
      mobile: false,
      mobileNav: false,
      windowWidth: null,
      scrolledNav: false

    };
  },
  created() {
    window.addEventListener('resize', this.checkScreen);
    this.checkScreen();
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  },
  methods: {
    toggleNav() {

      this.mobileNav = !this.mobileNav;

    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 900) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },
    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrolledNav = true;
        return;
      }
      this.scrolledNav = false;
      return;
    }
  }
};

</script>

<template>
  <header>
    <!--  delete  && !mobile if transparency of main navbar also in mobile version -->
    <nav :class="{ 'scrolled-nav-main': scrolledNav && !mobile }">
      <div class="nav-inner" id="myTopnav">
        <div class="logo">
          <img class="logoblog" src="@/assets/images/Blog.png" alt="">
        </div>

        <div class="link" v-if="!mobile">
          <a href="#">HOME</a>
          <a href="#">ARTICOLI</a>
          <a href="#">CHI SIAMO</a>
          <a href="#">CONTATTI</a>
        </div>

        <div class="iconBurger">
          <font-awesome-icon @click="toggleNav" icon="fas fa-bars" :style="{ width: '30px', height: '30px' }"
            :class="{ 'icon-active': mobileNav, 'icon-inactive': !mobileNav }" />
        </div>


        <div class="icons">
          <span class="icon">
            <svg width="30" height="30" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M22.0564 0.00246071C23.5158 -0.00313955 24.9752 0.0115282 26.4343 0.0464594L26.8222 0.0604588C27.2702 0.0764583 27.7122 0.0964575 28.2462 0.120457C30.3741 0.220453 31.8261 0.556442 33.1 1.05043C34.42 1.55841 35.5319 2.24638 36.6439 3.35835C37.6606 4.35752 38.4475 5.56616 38.9498 6.90023C39.4438 8.17418 39.7798 9.62813 39.8798 11.7561C39.9038 12.288 39.9238 12.732 39.9398 13.18L39.9518 13.568C39.9873 15.0263 40.0027 16.4851 39.9978 17.9439L39.9998 19.4358V22.0557C40.0047 23.5151 39.9894 24.9746 39.9538 26.4336L39.9418 26.8215C39.9258 27.2695 39.9058 27.7115 39.8818 28.2455C39.7818 30.3734 39.4418 31.8254 38.9498 33.0993C38.4491 34.4348 37.6621 35.6444 36.6439 36.6432C35.6439 37.6598 34.4346 38.4467 33.1 38.9491C31.8261 39.4431 30.3741 39.7791 28.2462 39.8791C27.7122 39.9031 27.2702 39.9231 26.8222 39.9391L26.4343 39.9511C24.9753 39.9867 23.5158 40.002 22.0564 39.9971L20.5645 39.9991H17.9465C16.4871 40.004 15.0277 39.9887 13.5687 39.9531L13.1807 39.9411C12.7059 39.9239 12.2313 39.9039 11.7568 39.8811C9.62883 39.7811 8.17688 39.4411 6.90092 38.9491C5.56633 38.4478 4.35748 37.6608 3.35904 36.6432C2.34116 35.6438 1.55355 34.4344 1.05112 33.0993C0.557135 31.8254 0.221146 30.3734 0.12115 28.2455C0.0988763 27.7709 0.0788769 27.2963 0.0611519 26.8215L0.0511525 26.4336C0.0142809 24.9746 -0.00238701 23.5152 0.00115396 22.0557V17.9439C-0.00442778 16.4851 0.0102399 15.0263 0.0451526 13.568L0.0591521 13.18C0.0751515 12.732 0.0951508 12.288 0.11915 11.7561C0.219147 9.62613 0.555135 8.17618 1.04912 6.90023C1.55185 5.56551 2.341 4.3572 3.36104 3.36035C4.35879 2.34189 5.56689 1.55355 6.90092 1.05043C8.17688 0.556442 9.62683 0.220453 11.7568 0.120457L13.1807 0.0604588L13.5687 0.0504594C15.027 0.0136063 16.4858 -0.0030616 17.9445 0.00046092L22.0564 0.00246071ZM20.0005 10.0021C18.6755 9.98338 17.3601 10.2282 16.1306 10.7222C14.901 11.2163 13.782 11.9498 12.8384 12.8801C11.8948 13.8105 11.1456 14.919 10.6342 16.1414C10.1228 17.3638 9.8594 18.6757 9.8594 20.0008C9.8594 21.3259 10.1228 22.6377 10.6342 23.8601C11.1456 25.0825 11.8948 26.1911 12.8384 27.1214C13.782 28.0518 14.901 28.7853 16.1306 29.2793C17.3601 29.7734 18.6755 30.0182 20.0005 29.9994C22.6525 29.9994 25.196 28.9459 27.0713 27.0706C28.9466 25.1953 30.0001 22.6519 30.0001 19.9998C30.0001 17.3477 28.9466 14.8043 27.0713 12.929C25.196 11.0537 22.6525 10.0021 20.0005 10.0021ZM20.0005 14.002C20.7975 13.9873 21.5894 14.1316 22.33 14.4264C23.0706 14.7212 23.745 15.1606 24.3139 15.719C24.8827 16.2774 25.3346 16.9435 25.6432 17.6785C25.9517 18.4135 26.1107 19.2026 26.1108 19.9998C26.1109 20.7969 25.9522 21.586 25.6439 22.3211C25.3357 23.0562 24.884 23.7225 24.3153 24.2811C23.7466 24.8397 23.0723 25.2793 22.3318 25.5744C21.5913 25.8695 20.7995 26.014 20.0025 25.9996C18.4112 25.9996 16.8852 25.3675 15.76 24.2423C14.6348 23.1171 14.0027 21.591 14.0027 19.9998C14.0027 18.4085 14.6348 16.8825 15.76 15.7573C16.8852 14.6321 18.4112 14 20.0025 14L20.0005 14.002ZM30.5001 7.00222C29.8549 7.02805 29.2447 7.30251 28.7974 7.76814C28.35 8.23376 28.1002 8.85443 28.1002 9.50014C28.1002 10.1458 28.35 10.7665 28.7974 11.2321C29.2447 11.6978 29.8549 11.9722 30.5001 11.9981C31.1631 11.9981 31.799 11.7347 32.2678 11.2658C32.7367 10.797 33 10.1612 33 9.49814C33 8.83512 32.7367 8.19926 32.2678 7.73043C31.799 7.26161 31.1631 6.99822 30.5001 6.99822V7.00222Z"
                fill="white" />
            </svg>
          </span>
          <span class="icon">
            <svg width="30" height="30" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M20 0C9 0 0 9 0 20C0 31 9 40 20 40C31 40 40 31 40 20C40 9 31.1 0 20 0ZM27.5 29.3C22.8 26.4 16.9 25.8 9.9 27.4C9.2 27.6 8.6 27.1 8.4 26.5C8.2 25.8 8.7 25.2 9.3 25C16.9 23.3 23.5 24 28.7 27.2C29.4 27.5 29.5 28.3 29.2 28.9C28.8 29.5 28.1 29.7 27.5 29.3ZM29.5 23.9C24.1 20.6 15.9 19.6 9.6 21.6C8.8 21.8 7.9 21.4 7.7 20.6C7.5 19.8 7.9 18.9 8.7 18.7C16 16.5 25 17.6 31.2 21.4C31.8 21.7 32.1 22.7 31.6 23.4C31.1 24.1 30.2 24.4 29.5 23.9ZM8.598 15.5C7.598 15.8 6.598 15.2 6.298 14.3C5.998 13.3 6.598 12.3 7.498 12C14.598 9.9 26.298 10.3 33.698 14.7C34.598 15.2 34.898 16.4 34.398 17.3C33.898 18 32.698 18.3 31.798 17.8C25.398 14 14.698 13.6 8.598 15.5Z"
                fill="white" />
            </svg>
          </span>
        </div>
      </div>

      <transition name="mobile-nav">
        <ul class="link-mobile" v-if="mobileNav" :class="{ 'scrolled-nav': scrolledNav }">
          <li><a href="#">HOME</a></li>
          <li><a href="#">ARTICOLI</a></li>
          <li><a href="#">CHI SIAMO</a></li>
          <li><a href="#">CONTATTI</a></li>
          <li>

            <span class="icon-mobile">
              <svg width="30" height="30" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M22.0564 0.00246071C23.5158 -0.00313955 24.9752 0.0115282 26.4343 0.0464594L26.8222 0.0604588C27.2702 0.0764583 27.7122 0.0964575 28.2462 0.120457C30.3741 0.220453 31.8261 0.556442 33.1 1.05043C34.42 1.55841 35.5319 2.24638 36.6439 3.35835C37.6606 4.35752 38.4475 5.56616 38.9498 6.90023C39.4438 8.17418 39.7798 9.62813 39.8798 11.7561C39.9038 12.288 39.9238 12.732 39.9398 13.18L39.9518 13.568C39.9873 15.0263 40.0027 16.4851 39.9978 17.9439L39.9998 19.4358V22.0557C40.0047 23.5151 39.9894 24.9746 39.9538 26.4336L39.9418 26.8215C39.9258 27.2695 39.9058 27.7115 39.8818 28.2455C39.7818 30.3734 39.4418 31.8254 38.9498 33.0993C38.4491 34.4348 37.6621 35.6444 36.6439 36.6432C35.6439 37.6598 34.4346 38.4467 33.1 38.9491C31.8261 39.4431 30.3741 39.7791 28.2462 39.8791C27.7122 39.9031 27.2702 39.9231 26.8222 39.9391L26.4343 39.9511C24.9753 39.9867 23.5158 40.002 22.0564 39.9971L20.5645 39.9991H17.9465C16.4871 40.004 15.0277 39.9887 13.5687 39.9531L13.1807 39.9411C12.7059 39.9239 12.2313 39.9039 11.7568 39.8811C9.62883 39.7811 8.17688 39.4411 6.90092 38.9491C5.56633 38.4478 4.35748 37.6608 3.35904 36.6432C2.34116 35.6438 1.55355 34.4344 1.05112 33.0993C0.557135 31.8254 0.221146 30.3734 0.12115 28.2455C0.0988763 27.7709 0.0788769 27.2963 0.0611519 26.8215L0.0511525 26.4336C0.0142809 24.9746 -0.00238701 23.5152 0.00115396 22.0557V17.9439C-0.00442778 16.4851 0.0102399 15.0263 0.0451526 13.568L0.0591521 13.18C0.0751515 12.732 0.0951508 12.288 0.11915 11.7561C0.219147 9.62613 0.555135 8.17618 1.04912 6.90023C1.55185 5.56551 2.341 4.3572 3.36104 3.36035C4.35879 2.34189 5.56689 1.55355 6.90092 1.05043C8.17688 0.556442 9.62683 0.220453 11.7568 0.120457L13.1807 0.0604588L13.5687 0.0504594C15.027 0.0136063 16.4858 -0.0030616 17.9445 0.00046092L22.0564 0.00246071ZM20.0005 10.0021C18.6755 9.98338 17.3601 10.2282 16.1306 10.7222C14.901 11.2163 13.782 11.9498 12.8384 12.8801C11.8948 13.8105 11.1456 14.919 10.6342 16.1414C10.1228 17.3638 9.8594 18.6757 9.8594 20.0008C9.8594 21.3259 10.1228 22.6377 10.6342 23.8601C11.1456 25.0825 11.8948 26.1911 12.8384 27.1214C13.782 28.0518 14.901 28.7853 16.1306 29.2793C17.3601 29.7734 18.6755 30.0182 20.0005 29.9994C22.6525 29.9994 25.196 28.9459 27.0713 27.0706C28.9466 25.1953 30.0001 22.6519 30.0001 19.9998C30.0001 17.3477 28.9466 14.8043 27.0713 12.929C25.196 11.0537 22.6525 10.0021 20.0005 10.0021ZM20.0005 14.002C20.7975 13.9873 21.5894 14.1316 22.33 14.4264C23.0706 14.7212 23.745 15.1606 24.3139 15.719C24.8827 16.2774 25.3346 16.9435 25.6432 17.6785C25.9517 18.4135 26.1107 19.2026 26.1108 19.9998C26.1109 20.7969 25.9522 21.586 25.6439 22.3211C25.3357 23.0562 24.884 23.7225 24.3153 24.2811C23.7466 24.8397 23.0723 25.2793 22.3318 25.5744C21.5913 25.8695 20.7995 26.014 20.0025 25.9996C18.4112 25.9996 16.8852 25.3675 15.76 24.2423C14.6348 23.1171 14.0027 21.591 14.0027 19.9998C14.0027 18.4085 14.6348 16.8825 15.76 15.7573C16.8852 14.6321 18.4112 14 20.0025 14L20.0005 14.002ZM30.5001 7.00222C29.8549 7.02805 29.2447 7.30251 28.7974 7.76814C28.35 8.23376 28.1002 8.85443 28.1002 9.50014C28.1002 10.1458 28.35 10.7665 28.7974 11.2321C29.2447 11.6978 29.8549 11.9722 30.5001 11.9981C31.1631 11.9981 31.799 11.7347 32.2678 11.2658C32.7367 10.797 33 10.1612 33 9.49814C33 8.83512 32.7367 8.19926 32.2678 7.73043C31.799 7.26161 31.1631 6.99822 30.5001 6.99822V7.00222Z"
                  fill="white" />
              </svg>
            </span>
            <span class="icon-mobile">
              <svg width="30" height="30" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M20 0C9 0 0 9 0 20C0 31 9 40 20 40C31 40 40 31 40 20C40 9 31.1 0 20 0ZM27.5 29.3C22.8 26.4 16.9 25.8 9.9 27.4C9.2 27.6 8.6 27.1 8.4 26.5C8.2 25.8 8.7 25.2 9.3 25C16.9 23.3 23.5 24 28.7 27.2C29.4 27.5 29.5 28.3 29.2 28.9C28.8 29.5 28.1 29.7 27.5 29.3ZM29.5 23.9C24.1 20.6 15.9 19.6 9.6 21.6C8.8 21.8 7.9 21.4 7.7 20.6C7.5 19.8 7.9 18.9 8.7 18.7C16 16.5 25 17.6 31.2 21.4C31.8 21.7 32.1 22.7 31.6 23.4C31.1 24.1 30.2 24.4 29.5 23.9ZM8.598 15.5C7.598 15.8 6.598 15.2 6.298 14.3C5.998 13.3 6.598 12.3 7.498 12C14.598 9.9 26.298 10.3 33.698 14.7C34.598 15.2 34.898 16.4 34.398 17.3C33.898 18 32.698 18.3 31.798 17.8C25.398 14 14.698 13.6 8.598 15.5Z"
                  fill="white" />
              </svg>
            </span>

          </li>
        </ul>
      </transition>
    </nav>

    <div class="row">
      <div class="col">

        <h1>Green Wind</h1>
        <p>

          Benvenuti nel nostro blog dedicato ai cambiamenti climatici, un problema urgente e complesso che sta plasmando
          il nostro presente e determinerà il futuro del pianeta. Qui esploriamo le sfide ambientali che stiamo
          affrontando e promuoviamo soluzioni innovative per mitigare gli effetti devastanti del cambiamento climatico.
        </p>
      </div>
    </div>


  </header>
</template>

<style scoped>
.container {
  margin: 0px 0px 0px 0px;
  padding: 0px 0px 0px 0px;
}

.logoblog {
  width: 50px;
  height: 50px;
  margin-left: 30px;
}

nav .nav-inner {

  height: 100px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #2D403A;
  opacity: 1;
  transition: opacity 0.5s ease;
}

.iconBurger {
  display: none
}

.nav-inner .link a {
  margin: 0px 20px;
  font-family: Helvetica;
  text-decoration: none;
  font-style: normal;
  font-size: 15px;
  font-weight: 400;
  color: white;
  line-height: 1.25;
  border-bottom: 1px solid transparent;
  transition: .3s;
}



.nav-inner .link a:hover {

  border-color: #ffffff;
}

.icons {
  display: flex;
  align-items: center;
}

.icons span {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 30px;
  cursor: pointer;
}

.icon-mobile {
  margin: 10px;
  cursor: pointer;
}

h1 {
  margin-top: 30px;
  font-family: Helvetica;
  font-weight: bold;
  font-size: 30px;
  margin-left: 70px;
  margin-right: 70px;
}

p {
  font-family: Helvetica;
  font-size: 20px;
  margin-left: 70px;
  margin-right: 70px;
  padding: 0px 0px;
}

nav {
  margin-left: 0px;
  width: 100%;
}



ul {
  list-style: none;
  text-decoration: none;
  font-weight: 500;
}

li {
  text-transform: uppercase;
  padding: 16px;
  margin-left: 16px;

}

.link-mobile li a {
  margin: 0px 20px;
  font-family: Helvetica;
  text-decoration: none;
  font-style: normal;
  font-size: 15px;
  font-weight: 400;
  color: rgb(255, 255, 255);
  line-height: 1.25;
  border-bottom: 1px solid transparent;
  transition: .3s;


}

.link-mobile {
  text-align: center;
  background-color: #2D403A;
  opacity: 1;
  transition: opacity 0.5s ease;

}

.link-mobile a:hover {

  border-color: #ffffff;
}

.icon-inactive {
  transform: rotate(0deg);
  transition-duration: 1s;
}

.icon-active {
  transform: rotate(180deg);
  transition-duration: 1s;

}

.scrolled-nav {
  background-color: #2D403A;
  opacity: 0.8;
  transition: opacity 0.5s ease;

}

.scrolled-nav-main .nav-inner {
  background-color: #2D403A;
  opacity: 0.8;
  transition: opacity 0.5s ease;
}

nav {

  position: fixed;
  top: 0;
  z-index: 999;
}

.row {
  margin-top: 100px;
}


.mobile-nav-enter-active,
.mobile-nav-leave-active {
  transition: 1s ease all;

}

.mobile-nav-enter-from,
.mobile-nav-leave-to {
  transform: translateY(-400px);
  z-index: -1;
}

.mobile-nav-enter-to {
  transform: translateX(0);
  z-index: -1;
}

/* @media (max-width: 768px) {
    .nav-inner {
      flex-direction: column;
    }
  
    .link {
      justify-content: center;
      margin-top: 10px;
    }
  
    .icon {
      justify-content: center;
      margin-top: 10px;
    }
    .icon span {
      display: flex;
      justify-content: center;
      align-items: center;
    }
  } */


@media screen and (max-width: 900px) {

  nav .nav-inner {
    align-items: right;
  }

  .nav-inner a {
    display: none;
  }

  .nav-inner .icons {
    display: none;
  }

  .nav-inner .iconBurger {
    float: right;
    display: block;
    cursor: pointer;
    color: #ffffff;
    margin-right: 10px;
  }
}
</style>

