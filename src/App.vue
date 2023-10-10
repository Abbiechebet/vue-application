<template>
    <navbar
     :pages="pages"
     :active-page="activePage"
     :nav-link-click="(index) => activePage = index">
     </navbar>

     <!-- v-show uses css to hide elements' contents -->
     <!-- <div v-show ="false">Hide this content</div> -->

     <!-- v-if when set to false won't show at all -->

     <!-- <page-viewer
       v-if="pages.length > 0"
       :page="pages[activePage]">
     </page-viewer> -->

     <create-page
      :page-created="pageCreated"
    ></create-page>

   </template>

 <script>
 import Navbar from "./components/Navbar.vue";
 import PageViewer from "./components/PageViewer.vue";
 import CreatePage from "./components/createPage.vue";
 
 export default {
   components: {
     Navbar,
     PageViewer,
     CreatePage
   },
   created(){
    this.getPages();
   },
   data() {
     return {
       activePage: 0,
       pages: []
     };
   },
   methods: {
    async getPages(){
      let res = await fetch('pages.json');
      let data = await res.json();

      this.pages = data;
    },
    pageCreated(pageObj) {
      this.pages.splice(this.pages.length, 0, pageObj);

    }
   }
 };
 </script>
 