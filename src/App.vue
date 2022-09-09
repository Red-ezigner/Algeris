<template>
  <div style="height: 100vh;">
    <Navbar />
      <!-- <button @click="get">click me </button> -->
      <div class="container app d-flex justify-content-center align-items-center">
        <div class="app2 row">
          <div class="row">
            <div class="col">
              <h1>Willaya</h1>  
            </div>
            <div class="col">
              <div class="d-grid gap-2">
                <span>{{ picked }}</span>
                <button class="btn btn-primary" type="button" @click="change">Change ar to ascii</button>
              </div>
            </div>
          </div>
          <div class="col text-center app3 ">
            
            <ul class="list-group">
              <li v-for="i in item" :key={i} class="list-group-item" @click="getDairat(i)" style="cursor: pointer;">{{i}}</li>
            </ul>

          </div>
          <div class="col text-center app3">


            <div class="card ">
              <h1>{{ name }}</h1>
              <h2>Daira count : {{ Daira_count }}</h2>
              
              <ul class="list-group">
                <li v-for="i in itemD" :key={i} class="list-group-item" style="cursor: pointer;">
                  <span v-if="picked == 'ASCII'"> 
                    <span v-if="i.dairaNameASCII=='AFLOU'" style="font-weight: bold;">{{i.dairaNameASCII }}</span>
                    <span v-else >{{i.dairaNameASCII }}</span>
                  </span>
                  <span v-else> 
                    <span v-if="i.dairaNameAR=='أفلو'" style="font-weight: bold;">{{ i.dairaNameAR }}</span>
                    <span v-else >{{ i.dairaNameAR }}</span>
                  </span>
                  
                </li>
              </ul>
            </div>



          </div>
        </div>
      </div>

    <Footer class="fixed-bottom" />
  </div>
</template>

<script>
import {
    getAllWillayaAR,
    getAllWillayaASCII,
    getWNameAR,
    getWByASCII
    // getWByID,
  //   getDairaASCII,
} from "states-alg";
import Navbar from './components/navbar.vue';
import Footer from './components/footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      item: [],
      itemD: [],
      name: '',
      Daira_count: '',
      picked: 'ASCII',
      select: null
    }
  },
  async mounted() {
    this.get(this.picked);
  }, 
  methods: {
    getDairat(i) {
      this.select = i;
      let t = (this.picked === "ASCII")? getWByASCII(this.select):getWNameAR(this.select);
      if(t){
        this.name = this.select;
        this.Daira_count = t.daira.length;
        this.itemD = t.daira;
      }
    },
    change() {
      this.picked = (this.picked === "ASCII")? "العربية":"ASCII";
      this.get();
      this.getDairat(this.select);
    },
    get() {
      if(this.picked == 'ASCII'){
        this.item = getAllWillayaASCII();
      }
      if(this.picked == 'العربية'){
        this.item = getAllWillayaAR();
      }
    }
  },
}
</script>

<style>
  .app{
    height: 70vh;
  }

  .app2{
    height: 60%;
    width: 100%;
  }

  .app3{
    height: 100%;
    width: 100%;
    overflow-y: scroll;
    margin: 10px;
    
  }
</style>
