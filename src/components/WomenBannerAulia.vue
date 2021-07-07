<template>
    <!-- Women Banner Section Begin -->
    <section class="women-banner spad">
        <div class="container-fluid">
            <div class="row">
                <div class="col-lg-12 mt-5" v-if="products.lenght !=0" >
                    <carousel 
                        class="product-slider" 
                        :items="5"
                        :dots="false" 
                        
                        :autoplay="true" 
                        :nav="false" 
                    >
                        <div 
                            class="product-item" 
                            v-for="itemProducts in products" 
                            v-bind:key="itemProducts.id"
                        >
                            <div class="pi-pic">
                                <img v-bind:src="itemProducts.galleries[0].photo" alt="" />
                                <ul>
                                    <li class="w-icon active">
                                        <router-link to="/product">
                                        <i class="icon_bag_alt"></i>
                                        </router-link>
                                    </li>
                                    <li class="quick-view">
                                        <router-link to="/product">+ View Product</router-link>
                                        <!-- <a href="product.html">+ Quick View</a> -->
                                    </li>
                                </ul>
                            </div>
                            <div class="pi-text">
                                <div class="catagory-name">{{ itemProducts.type }}</div>
                                    <router-link to="/product">
                                        <h5>{{ itemProducts.name }}</h5>
                                    </router-link> 
                                <div class="product-price">
                                    {{ itemProducts.price }}
                                    <span>Rp 150.000,-</span>
                                </div>
                            </div>
                        </div>
                    </carousel>
                </div>
                <div  v-else>
                    <p>Data tidak ditemukan</p>
                </div>
            </div>
        </div>
    </section>
    <!-- Women Banner Section End -->
</template>

<script>
import carousel from 'vue-owl-carousel';
import axios from 'axios';

export default {
   name: 'WomenBannerAulia',
   components: {
       carousel
   },
   data(){
       return{
           products:[]
       };
   },
   mounted(){
       axios
       .get("http://127.0.0.1:8000/api/products")
       .then(res => (this.products = res.data.data.data))
       //eslint-disable-next-line no-console
       .catch(err => console.log(err));
   }
}
</script>