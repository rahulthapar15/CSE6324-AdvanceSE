<template>
  <div id="app">

    <div class="sidenav">
      <!-- <a href="">Publication Venues</a>
      <a href="">Research Papers</a> -->
      <img src="./images/logo.png" alt="">

      <div class="items">
        <p class="nav-head--item" @click.prevent="selectTab('home')">Home</p>
      </div>

      <div style="margin-top:30px;" class="items">
        <p class="nav-head">Project Phases</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-1')">Phase 1</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-2')">Phase 2</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-3')">Phase 3</p>
      </div>

      <div class="items">
        <p class="nav-head">Download</p>
        <p class="nav-head--item">Literature Review</p>
        <p class="nav-head--item">Presentation</p>
        <p class="nav-head--item">Technical Report</p>
      </div>

      <div class="items">
        <p class="nav-head">Resources</p>
        <p class="nav-head--item" @click.prevent="selectTab(0)">Research Papers</p>
        <p class="nav-head--item" @click.prevent="selectTab(1)">Publication Venues</p>
      </div>
      

    </div>

    <div class="main">
      <div class="section">
        <h3>CSE 6324: Advance Topics in Software Engineering</h3>
        <br>
       <information :data=selectedTab></information>
      </div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Information from './components/Information.vue'

export default {
  name: 'App',
  data(){
    return{
      selectedTab: "About"
    }
  },
  methods:{
    selectTab : function(tab){
      var vm = this
      switch(tab){
        case 0: vm.selectedTab = 'Research Papers'
        break;

        case 1: vm.selectedTab = 'Publication Venues'
        break;

        case 'ph-1': vm.selectedTab = "Phase 1"
        break;

        case 'ph-2': vm.selectedTab = "Phase 2"
        break;

        case 'ph-3': vm.selectedTab = "Phase 3"
        break;

        case 'home' : vm.selectedTab = "About"
        break;

        default: vm.selectedTab = ''
        break;
      }
    }
  },
  components: {
   // HelloWorld
   Information
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
* {
  padding: 0;
  margin: 0;
  font-family: 'Roboto', sans-serif;
}
#app{
 
}
.sidenav {
  height: 100%;
  width: 360px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #F0F2F4;
  overflow-x: hidden;
  padding-top: 50px;
}

.items{
  padding-left: 20px;
  margin-top: 50px;
}
.nav-head{
  font-size: 18px;
  font-weight: 900;
  color: #B7C6CC;
  margin-bottom: 15px;
}

.nav-head--item{
  margin-top: 8px;
  font-size: 16px;
  color: #818181;
}
.nav-head--item:hover{
  cursor: pointer;
  color: #40A5AD;
}

.sidenav a {
  padding: 6px 8px 6px 26px;
  text-decoration: none;
  font-size: 20px;
  color: #818181;
  display: block;
}

.sidenav img{
  width: 250px;
  height: 120px;
}

.sidenav a:hover {
  color: #4E5463;
}

.main {
  margin-left: 360px; /* Same as the width of the sidenav */
  font-size: 28px; /* Increased text to enable scrolling */
  padding: 0px 10px;
}
.section{
  padding: 20px 20px 0px 40px;
}

@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}
</style>
