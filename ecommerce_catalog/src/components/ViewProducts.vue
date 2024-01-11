<template>
     <div class="container">  
          <div class="box">
               
          </div>
     <!--  <li v-for="item in products" :key="item.id">{{ item.category}}</li> -->
     </div>
    
</template>

<script>
export default {
     data(){
          return {
               products: []
          };
     },
     methods:{
          async fetchData() {
               const response = await fetch('https://fakestoreapi.com/products');
               const result = await response.json();
              
               result.forEach((r) => {
                    if ( r['category'] == "men's clothing" || r['category'] == "women's clothing" ) {
                         this.products.push(r);
                    }
               });
             
               return this.products;
          }  
     },
     created() {
          this.fetchData();
     },
};

</script>

<style scoped>
div {
 
  padding: 1em;
  max-width: 75%;
}
.container {
  border: solid 3px;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 8em;
}
.women-section {

}
.man-section {
     background-color: #D6E6FF;
     position: fixed;
     top: 0;
     left: 0;
     width: 100%;
     height: 70%;                  
}
.product-unavailable {
                              
}

.navi {
     color:
}
</style>