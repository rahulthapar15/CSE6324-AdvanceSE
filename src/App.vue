<template>
  <div id="app">

    <div class="sidenav">
      <!-- <a href="">Publication Venues</a>
      <a href="">Research Papers</a> -->
      <img src="./images/logo.png" alt="">

      <div class="items">
        <p class="nav-head--item" @click.prevent="selectTab('home')">Home</p>
      </div>
<!-- 
      <div style="margin-top:30px;" class="items">
        <p class="nav-head">Project Phases</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-1')">Phase 1</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-2')">Phase 2</p>
        <p class="nav-head--item" @click.prevent="selectTab('ph-3')">Phase 3</p>
      </div> -->

      <div class="items">
        <p class="nav-head">Download</p>
        <p class="nav-head--item">Literature Review</p>
        <p class="nav-head--item">Presentation</p>
      </div>

      <div class="items">
        <p class="nav-head">Resources</p>
        <p class="nav-head--item" @click.prevent="selectTab(0)">Research Papers</p>
        <p class="nav-head--item" @click.prevent="selectTab(1)">Publication Venues</p>
      </div>
      

    </div>

    <div class="main">
      <div class="section">
        <h3>CSE 6324: Advance Topics in Software Engineering</h3><br>
        <div v-if="!showInfotabs" class="txt-info">
          <hr>
        <p class="txt-info">Rahul Thapar <br> University of Texas, Arlington <br> Department of Computer Science <br>rahul.thapar@mavs.uta.edu</p>
        <hr><br>
          <p>The aim of this project was to write a literature review on one of the following :</p><br>
          <li>Memory consistency model</li>
          <li>Lock-free/wait-free synchronization</li>
          <li>Data race detection</li>
          <li>Concurrency testing</li>
          <li>Formal verification </li>
          <br>
          <hr><br>
          <p>The topic chosen was: <label class="color-red bold">Data Race Detection</label></p>
          <br>
          <p>The literature review includes:</p>
          <li>Static vs Dynamic Data race detectors</li>
          <li>Dynamic Race Detection Tools, Evaluation and Comparison which</li>
          <li>Information about FastTrack, GoldiLocks, Multi-race, Djit+ and Eraser</li>
          <li>Approach analysis of the above tools</li>
          <li>Performance Comparison of all tools with FastTrack</li>
          <li>FastTrack on Eclipse Environment to check Race Conditions</li>
          <li>Result to summarise the findings from the above comparison.</li>
        </div>
        <br>
       <information v-if="showInfotabs" :data=data></information>
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
      showInfotabs: false,
      selectedTab: "About",
      data:{
        selectedTab: "",
        info: "",
        list: []
      }
    }
  },
  methods:{
    selectTab : function(tab){
      var vm = this
      switch(tab){
        case 0: 
          vm.showInfotabs = true
          vm.data.selectedTab = 'Research Papers'
          vm.data.info = 'Following are the major research papers that were taken as the base study for this literature review.'
          vm.data.list = []
          vm.data.list.push({
            text: "Evaluation and comparison of ten data race detection techniques",
            link: "https://www.researchgate.net/publication/319672758_Evaluation_and_comparison_of_ten_data_race_detection_techniques"
          })
          vm.data.list.push({
            text: "Predicting All Data Race Pairs for a Specific Schedule",
            link: "https://arxiv.org/pdf/1909.03289.pdf"
          })
          vm.data.list.push({
            text: "Goldilocks: A race and transaction-aware Java runtime",
            link: "https://www.cs.purdue.edu/homes/xyzhang/fall07/Papers/goldilock.pdf"
          })
          vm.data.list.push({
            text: "Goldilocks: Efficiently Computing the Happens-Before Relation Using Locksets",
            link: "https://www.researchgate.net/publication/221366250_Goldilocks_Efficiently_Computing_the_Happens-Before_Relation_Using_Locksets"
          })
          vm.data.list.push({
            text: "Experimental Performance Comparison of Dynamic Data Race Detection Techniques",
            link: "https://onlinelibrary.wiley.com/doi/pdf/10.4218/etrij.17.0115.1027"
          })
          vm.data.list.push({
            text: "Case Study of Dynamic Detectors for Data Races",
            link: "https://www.sciencedirect.com/science/article/pii/S2212667813000282"
          })
          vm.data.list.push({
            text: "An Efficient Algorithm for On-the-Fly Data Race Detection Using an Epoch-Based Technique",
            link: "http://downloads.hindawi.com/journals/sp/2015/205827.pdf"
          })
          vm.data.list.push({
            text: "Eraser: A Dynamic Data Race Detector for Multithreaded Programs",
            link: "https://homes.cs.washington.edu/~tom/pubs/eraser.pdf"
          })
          vm.data.list.push({
            text: "Reachability Testing of Concurrent Programs",
            link: "http://ranger.uta.edu/~ylei/data/TSERT.pdf"
          })
          vm.data.list.push({
            text: "Verifying Dynamic Race Detection",
            link: "https://www.cs.uic.edu/~mansky/rd.pdf"
          })
          vm.data.list.push({ text: '...other sources are linked in the literature review paper.'})
        break;

        case 1: 
          vm.showInfotabs = true
          vm.data.selectedTab = 'Publication Venues'
          vm.data.info = 'Following are the publication venues for the papers referred to write the literature review:'
          vm.data.list = []
          vm.data.list.push({
            text: "Evaluation and comparison of ten data race detection techniques",
            venue: "December 2016 : International Journal of High Performance Computing and Networking"
          })
          vm.data.list.push({
            text: "Predicting All Data Race Pairs for a Specific Schedule",
            venue: "[Submitted on 7 Sep 2019]"
          })
          vm.data.list.push({
            text: "Goldilocks: A race and transaction-aware Java runtime",
            venue: "Not Available"
          })
          vm.data.list.push({
            text: "Goldilocks: Efficiently Computing the Happens-Before Relation Using Locksets",
            venue: "[December 2005] : https://dblp.uni-trier.de/db/conf/fates/fates2006.html"
          })
          vm.data.list.push({
            text: "Experimental Performance Comparison of Dynamic Data Race Detection Techniques",
            venue: "ETRI Journal, Volume 39, Number 1, February 2017 https://doi.org/10.4218/etrij.17.0115.1027"
          })
          vm.data.list.push({
            text: "Case Study of Dynamic Detectors for Data Races",
            venue: "2013 International Conference on Electronic Engineering and Computer Science"
          })
          vm.data.list.push({
            text: "An Efficient Algorithm for On-the-Fly Data Race Detection Using an Epoch-Based Technique",
            venue: "Hindawi Publishing Corporation Scientific Programming Volume 2015, Article ID 205827, 14 pages http://dx.doi.org/10.1155/2015/205827"
          })
          vm.data.list.push({
            text: "Eraser: A Dynamic Data Race Detector for Multithreaded Programs",
            venue: "ACM Transactions on Computer Systems, Vol. 15, No. 4, November 1997"
          })
          vm.data.list.push({
            text: "Reachability Testing of Concurrent Programs",
            venue: " IEEE TRANSACTIONS ON SOFTWARE ENGINEERING, VOL. 32, NO. 6, JUNE 2006"
          })
          vm.data.list.push({
            text: "Verifying Dynamic Race Detection",
            venue: "Not Available"
          })
        break;

        case 'ph-1': vm.selectedTab = "Phase 1"
        break;

        case 'ph-2': vm.selectedTab = "Phase 2"
        break;

        case 'ph-3': vm.selectedTab = "Phase 3"
        break;

        case 'home' :
            vm.showInfotabs = false
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

.txt-info{
  font-size: 14px;
  color: #4E5463;
  line-height: 1.5em;
}

.color-red{
  color: #40A5AD;
}

.bold{
  font-weight: 900;
}

@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}
</style>
