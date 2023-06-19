<script >

import Header from './components/Header.vue'
import PortfolioItem from './components/PortfolioItem.vue'
import SocialLink from './components/SocialLink.vue'
import Footer from './components/Footer.vue'


import contentsData from './assets/contents.json'

export default {
  data() {
    return {
      contents: contentsData,
    };
  },
  components: {
    Header,
    PortfolioItem,
    SocialLink,
    Footer,
  },
};

</script> 

<template>
  <main>
    <Header></Header>

    <div id="works" class="row">
      <div class="col-12 col-md-6" v-for="work in contents.works" :key="work.id">
         <PortfolioItem 
          :title="work.title"
          :abstract="work.description"
          :imageUrl="work.image_thumbnail"
        />
      </div>
    </div>

    <div id="social-links" class="row">
      <ul>
        <li v-for="link in contents.social_links" :key="link.id">
          <SocialLink 
            :id="link.id"
            :name="link.name"
            :url="link.url"
          />
        </li>
      </ul>
    </div>
    <Footer></Footer>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
