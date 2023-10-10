<template>
<a 
     class="nav-link" 
     :class="activeClasses"
     arial-current="page" 
     :href="page.Link.url"
     :title="`This link goes to the ${page.Link.text} page`"                   
>{{ page.Link.text }}</a>
</template>

<script>
export default {
    props:['page', 'isActive'],
    computed: {
        activeClasses() {
            return{
                active: this.isActive,
                emphasize: this.isActive
            };
        }
    }
}
</script>

<style scoped>
.emphasize{
    text-decoration: underline !important;
}
</style>