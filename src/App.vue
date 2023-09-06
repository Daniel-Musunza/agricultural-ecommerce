<template>
  <div>
    <section class="section1">
                <header>
                <div class="header1">
                    <span class="site-logo-img">
                        <div rel="home" aria-current="page">
                            <h3 class="custom-logo">Kenyan Farm</h3>
                            
                        </div>
                    </span> 
                    
                    <div class="header1-links">
                        <div class="link"><router-link to="/">Producers</router-link></div>
                        <div class="link"><router-link to="/about">Why Us?</router-link> </div>
                        <div class="link"><router-link to="/blog">The Green Life</router-link></div>
                        <div class="link">FAQs</div>
                        <div class="link"><router-link to="/shop">Shop Now</router-link></div>
                    </div>
                    <div  v-if="!user" class="hello-login">
                        <div class="hello-guest">
                            Hello Guest!
                        </div>
                        <div  class="login-or-signup">
                            <router-link to="/signIn">Login /</router-link>
                            <router-link to="/signUp">Sign Up</router-link>
                        </div>
                    </div>
                    <div  v-if="user" class="hello-login">
                        <div class="hello-guest">
                            <router-link clas="option" to="/profile">
                                <h3>{{ this.$store.state.profileFirstName }} {{this.$store.state.profileLastName }}</h3>
                            </router-link>
                            
                        </div>
                        <div  class="login-or-signup">
                            <div><router-link to="/administration">Post Product</router-link></div>
                            <div class='logout' @click="signOut()">Logout</div>
                        </div>
                    </div>
                </div>
                </header>
                <div class="search-part">
                    
                    <input placeholder="Search for honestly delicious goodies..." class="search-form-input" />
                </div>
                <header>
                    <div class="header2">
                        <ul class="header2-list">
                            <li>
                                <div class="small-sections-header" @click="toggleDairy()">
                                    <span>Dairy</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleLivestockAndPoutry" class="small-sections-header">
                                    <span>Livestock and Poultry</span>
                                </div>
                                
                            </li>
                            <li>
                                <div @click="toggleSeafood" class="small-sections-header">
                                    <span>Seafood</span>
                                </div>
                                
                            </li>
                            <li>
                                <div @click="toggleEggs" class="small-sections-header">
                                    <span>Eggs</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleFruits" class="small-sections-header">
                                    <span>Fruits</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleVegetables" class="small-sections-header">
                                    <span>Vegetables</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleGrainsAndCereals" class="small-sections-header">
                                    <span>Grains and Cereals</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleLegumes" class="small-sections-header">
                                    <span>Legumes</span>
                                </div>
                               
                            </li>
                            <li>
                                <div @click="toggleHerbsAndSpecies" class="small-sections-header">
                                    <span>Herbs and Spices</span>
                                </div>
                                
                            </li>
                            <li>
                                <div @click="toggleMiraaAndMogoka" class="small-sections-header">
                                    <span>Miraa and mogoka</span>
                                </div>
                                
                            </li>
                        </ul>
                    </div>
                   <div>
                    <div v-if="dairy" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Dairy</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Cheese</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <router-link :to="{ name: 'shop', params: { productBrand: 'Milk' } }"><span class="">Milk</span></router-link>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Yogurt</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Butter</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/milk.jpg" />
                                        <h3 class="hello-guest">Fresh Milk</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/butter.png" />
                                            <h3 class="hello-guest">Packed Butter</h3>
                                        </div>
                                        
                                    </section>
                    </div>
                    <div v-if="Livestockandpoutry" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Livestock and Poultry</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Beef</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Chicken</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Pork</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Lamb</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/bull.jpeg" />
                                            <h3 class="hello-guest">A Bull</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/chicken.jpg" />
                                            <h3 class="hello-guest">A Chicken</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="seafood" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Seafood</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Fish (Salmon, Tuna, etc.)</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Shrimp</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Crab</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Lobster</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/fish1.jpg" />
                                            <h3 class="hello-guest">Fish</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/fish2.jpeg" />
                                            <h3 class="hello-guest">Fish</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="eggs" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Eggs</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Chicken Eggs</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Duck Eggs</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/eggs.jpeg" />
                                            <h3 class="hello-guest">Chicken Eggs</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="fruits" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Fruits</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Apples</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Bananas</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Oranges</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Mangoes</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Pineapples</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Strawberries</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Water Mellon</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Grapes</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/apples.jpeg" />
                                            <h3 class="hello-guest">Apples</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/banana.jpeg" />
                                            <h3 class="hello-guest">Bananas</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="vegetables" class="small-sections-container" :class="{ 'overflowed': isOverflowed }">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Vegetables</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Tomatoes</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Carrots</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Broccoli</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Spinach</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Onions</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Cucumbers</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Cabbages</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Sukuma wiki</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Mchicha</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Ocra (Mabenda)</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Egg plant (rafaya)</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/carrots.jpeg" />
                                            <h3 class="hello-guest">Carrots</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/cabbages.jpeg" />
                                            <h3 class="hello-guest">Cabbages</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="grainsandcereals" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Grains and Cereals</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Wheat</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Rice</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Corn</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Barley</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Maize</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Sorghum</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Millet</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/maize.avif" />
                                            <h3 class="hello-guest">Dry Maize</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/sorghum.webp" />
                                            <h3 class="hello-guest">Sorghum</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="legumes" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Legumes</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Beans</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Peas</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">cow peas</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">green peas</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">pojo</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">pegeon peas</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/beans.jpg" />
                                            <h3 class="hello-guest">Beans</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/cowpeas.webp" />
                                            <h3 class="hello-guest">Cow Peas</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="herbsandspecies" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Herbs and Spices </span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Basil</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Rosemary</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Thyme</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Cilantro</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Mint</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Oregano</span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/basil.jpg" />
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/oregano.jpg" />
                                            <h3 class="hello-guest">Oregano</h3>
                                        </div>
                                    </section>
                    </div>
                    <div v-if="miraaandmogoka" class="small-sections-container">
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Miraa and Mogoka </span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <i></i>
                                                <span class="">Mbeere Mogoka</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Mchele Mogoka</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Kimeru Mogoka</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Kangeta Miraa</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class="">Gachoka miraa</span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class=""> Igembe miraa </span>
                                            </li>
                                            <li>
                                                <i></i>
                                                <span class=""> Mutuati miraa </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section">
                                        <div class="small-section-heading">
                                            <span>Shop Producers</span>
                                        </div>
                                        <ul class="small-section-list">
                                            <li>
                                                <span class="">Bio Food Products</span>
                                            </li>
                                            <li>
                                                <span class="">Browns Food Co. </span>
                                            </li>
                                        </ul>
                                    </section>
                                    <section class="small-section-images">
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/miraa.jpg" />
                                            <h3 class="hello-guest">Miraa</h3>
                                        </div>
                                        <div class="small-section-image">
                                            <img class="br-loaded" src="@/assets/img/mogoka.jpg" />
                                            <h3 class="hello-guest">Mogoka</h3>
                                        </div>
                                    </section>
                    </div>
                   </div>
                </header>
    </section>
    <div class="cart-opener" @click="toggleCart()">
            <div class="cart-unopened"><i class="fas fa-shopping-cart"></i><span> {{cartQuantity}} </span></div>
            <!-- <div class="cart-opened">X</div> -->
    </div>
    <CartView v-if="cart"/>
    <router-view/>
  </div>
</template>
<script>
import CartView from "@/components/Cart/CartView"
import firebase from "firebase/app"
import "firebase/auth"
export default {
  name: 'App',
  components: {
    CartView,
  },
  data (){
    return {
        navigation: null,
        cart: false,
        dairy: false,
        Livestockandpoutry: false,
        seafood: false,
        eggs: false,
        fruits: false,
        vegetables: false,
        grainsandcereals: false,
        legumes: false,
        herbsandspecies: false,
        miraaandmogoka: false,
    }
  },
  methods: {
    toggleCart(){
        this.cart = !this.cart
    },
    toggleDairy(){
        this.dairy = !this.dairy,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleLivestockAndPoutry(){
        this.Livestockandpoutry = !this.Livestockandpoutry,
        this.dairy = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleSeafood(){
        this.seafood = !this.seafood,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleEggs(){
        this.eggs = !this.eggs,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleFruits(){
        this.fruits = !this.fruits,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleVegetables(){
        this.vegetables = !this.vegetables,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleGrainsAndCereals(){
        this.grainsandcereals = !this.grainsandcereals,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.legumes = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleLegumes(){
        this.legumes = !this.legumes,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.herbsandspecies = false,
        this.miraaandmogoka = false
    },
    toggleHerbsAndSpecies(){
        this.herbsandspecies = !this.herbsandspecies,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.miraaandmogoka = false
    },
    toggleMiraaAndMogoka(){
        this.miraaandmogoka = !this.miraaandmogoka,
        this.dairy = false,
        this.Livestockandpoutry = false,
        this.seafood = false,
        this.eggs = false,
        this.fruits = false,
        this.vegetables = false,
        this.grainsandcereals = false,
        this.legumes = false,
        this.herbsandspecies = false
    },
    signOut() {
            firebase.auth().signOut();
            window.location.reload();
            this.$router.replace('/signIn');
      },
      checkScreen () {
        this.windowWidth = window.innerWidth;
        if (this.windowWidth <= 750) {
          this.mobile = true;
          return;
        }
        this.mobile = false;
        this.mobileNav = false;
        return;

      },
    checkRoute() {
        if (this.$route.path ==="/signIn" || this.$route.path === "/signUp" || this.$route.path === "/forgot-password"){
            this.navigation = true;
            return;
        }
        this.navigation = false;
        return;
    }
  },
  watch: {
    $route() {
    this.checkRoute();
    }
  },
  computed: {
    user() {
          return this.$store.state.user;
    },
    cartQuantity (){
      return this.$store.getters.cartQuantity;
    }
  },
  created() {
        this.checkRoute();
        firebase.auth().onAuthStateChanged(async (user) => {
            this.$store.commit("updateUser", user);
            if(user) {
                this.$store.dispatch("getCurrentUser", user)
            }
        })
        this.checkRoute();

        window.addEventListener("resize", this.checkSreen);
        this.checkScreen();
  }
}
</script>
<style scoped>
.logout{
    cursor: pointer;
}
.section1 {
    display: flex;
    flex-direction: column;
   top: 0;
    position: fixed;
    z-index: 999;
    width: 100%;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    background-color: #fff;
}

.header1 {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    background-color: #ffffff; /* Adding a background color for illustration */
    padding: 10px 20px;
    width: 100%;
}
.custom-logo
{
    color: rgb(19, 137, 4);
    font-size: 40px;
    font-weight: 800;
    text-decoration: none;
    padding: 0;
    margin: 0;
}

.header1-links {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    margin-left: 20px;
    font-size: 20px;
}

.hello-login {
    margin-right: 50px;
}
.hello-guest {
    font-size: 18px; /* Adjust the font size as needed */
    font-family: 'Lexend Deca', Helvetica, Arial, sans-serif; /* Italic font-family */
    font-style: italic;
}
.link {
    margin-right: 10px;
}

.search-part {
    display: flex;
    justify-content: center;
    margin: 20px;

}

.search-form-input {
    width: 40%;
    border-radius: 20px;
    border: 1px solid #ccc;
    padding: 10px;
}
.header2 {
    display: flex;
    justify-content: center;
    width: 100%;
    background-color: rgb(19, 137, 4);
    color: #fff;
   
}

.header2-list {
    display: flex;
    list-style: none;
    padding: 0;
    overflow-x: scroll;
    /* Add scrollbar styles */
}

.header2-list::-webkit-scrollbar {
    width: 10px; /* Width of the scrollbar */
}

.header2-list::-webkit-scrollbar-thumb {
    background-color: rgb(19, 137, 4); /* Color of the thumb */
    border-radius: 5px; /* Rounded corners for the thumb */
}

.header2-list::-webkit-scrollbar-track {
    background-color: rgb(19, 137, 4); /* Color of the track */
    border-radius: 5px; /* Rounded corners for the track */
}


.header2-list li {
    margin: 0 20px;
    cursor: pointer;
    position: relative;
    display: flex;
    flex-direction: column;
    
}
.small-sections-header{
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}
.small-sections-container {
  display: flex;
  position: relative;
  top: 30px;
  margin-top: 20px;
  background-color: #fff;
  border: 1px solid #ccc;
  color: black;
  border-radius: 4px;
  width: 100vw; /* Use viewport width for full screen width */
  max-height: 300px;
  flex-wrap: wrap;
  overflow: hidden; /* Hide overflow content */
}

.overflowed {
  flex-direction: column; /* Display the sections vertically */
  overflow-y: scroll; /* Enable vertical scrolling for overflowed content */
}

.small-section {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  margin: 30px;
}

.small-section-heading {
  font-size: 20px;
  padding-bottom: 20px;
  font-weight: 700;
}

.small-section-list {
  list-style: none;
  padding: 0;
  margin-top: 10px;
}

.small-section-list li {
    margin-bottom: 5px;
}
.small-section-image{
    margin: 10px;
}
.small-section-image img {
    max-width: 200px;
    height: auto;
}
.small-section-images{
    display: flex;
    flex-direction: row;
    margin-right: 10px;
}

.cart-opener {
    position: fixed;
    top: 150px; /* Adjust the top position as needed */
    right: 0; /* Display to the right */
    border-radius: 50%;
    background-color: green;
    border: 1px solid #000;
    font-size: 20px;
    width: 50px;
    height: 50px;
    z-index: 999;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
}

.cart-opener .fa-shopping-cart {
    color: white; /* Change the icon color as needed */
}

.cart-unopened span {
    color: #f5c200;
}
</style>
