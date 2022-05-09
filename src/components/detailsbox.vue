<template>
    
     <div class="detailsbox">
         
        <div v-for="det in products" :key="det.id" >
                <product :detail="det"/>
        </div>
     </div>

</template>

<script>

import product from "./details.vue"
export default{
  // eslint-disable-next-line vue/multi-word-component-names
    name: 'detailsbox',
    components: {
        product
    },
    props: {
        products: JSON
    }
}

</script>
<style>
.detailsbox{

    background-color: rgb(242, 246, 245);
    padding: 1em;
    color: #f6eeee;
  /*border-radius: 50px;*/
}
</style>