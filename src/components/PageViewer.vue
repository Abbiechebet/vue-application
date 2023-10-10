<template>
    <div class="container">
            <h1 class="emphasize">{{page.pageTitle}}</h1>
            <p> {{page.content}}</p>
       </div>
   </template>
   
   <script>
   export default{
       props: ['page']
       
    // an alternative for v-if

    // props: {
    //     page: {
    //         type: Object,
    //         default(rawProps){
    //             return{
    //                 pageTittle: '',
    //                 content: ''
    //             };
    //         }
    //     }
    // }
   }
   </script>
   
<style scoped>
.emphasize{
    color: goldenrod !important;
}
</style>