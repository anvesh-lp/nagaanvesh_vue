<template>
  <div class="container">
    
    <Header siteName="Health care"
      authorName="Naga Anvesh Kunuguntla"/>

    <detailsbox :products="products"  />

  </div>
</template>
<script>


import Header from './components/Header.vue'
import detailsbox from './components/detailsbox.vue'

export default {
  name: 'App',
  components: {
    
    Header,
    detailsbox
  },

  data(){
    return {
      products: []
    }
  },
  methods: {
      async fetchproducts(){
        const url='https://nagaanveshfinalproject.herokuapp.com/api';
        return new Promise((resolve, request)=>{
          try {
            fetch(url).then((res)=> {return res.json()}).then((res)=>{
              resolve(
                  res.map(pos=>({
                    ...pos
                  }))
              )
            });
          }catch (err){
            request(err);
          }
        })
      }
  },

  async created(){
    this.products = await this.fetchproducts()
    console.log(this.products);
  }
}
</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 70%;
  margin: 30px auto;
  overflow: auto;
  min-height: 500px;
  border: 0.3em solid #fcf0f0;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}

</style>


