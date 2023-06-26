<script >

import Header from './components/Header.vue'
import Blog from './components/Blog.vue'
import SocialLink from './components/SocialLink.vue'
import Footer from './components/Footer.vue'
import Articoli from './components/Articoli.vue'
import Subscribe from './components/Subscribe.vue'
import Latest from './components/Latest.vue'
import Uomo from './components/Uomo.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';





import contentsData from './assets/contents.json'

export default {
  data() {
    return {
      contents: contentsData,

    };
  },
  components: {
    Header,
    Articoli,
    Blog,
    Subscribe,
    SocialLink,
    Latest,
    Uomo,
    Footer,
    FontAwesomeIcon,
  },

};


</script> 

<template>
  <main>

    <Header></Header>



    <Articoli></Articoli>
    <div class="container">
      <div id="works" class="row">
        <div class="image-item col-12 col-md-4" v-for="work in contents.works" :key="work.id">
          <Blog :title="work.title" :abstract="work.description" :imageUrl="work.image_thumbnail" />
        </div>


        <!-- <div id="social-links" class="row">
            <ul>
              <li class="link" v-for="link in contents.social_links" :key="link.id">
                <SocialLink 
                  :id="link.id"
                  :name="link.name"
                  :url="link.url"
                />
              </li>
            </ul>
          </div>-->




      </div>
    </div>
    <Subscribe></Subscribe>
    <Latest></Latest>
    <Uomo></Uomo>
    <Footer></Footer>

  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  margin-left: 0px;
  margin-right: 0px;
}


.container {
  /* max-width: calc(1440 - 130px); */
  /* padding: 0 20px; */
  width: 100%;
  margin: auto;
}

#works {
  margin: 50px;
}




.open {
  transform: translateX(300px);
}

/*@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
*/
</style>
