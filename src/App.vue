<template>
  <el-container>
    <el-header height="120px">
      <NavBar />
      <SecondaryNav />
    </el-header>
    <el-container>
      <el-aside width="300px">
        <SideBar/>
      </el-aside>
      <el-container>
        <el-main>
          <div v-for="product in products" :key="product.id">
            <ProductCard :product="product" />
          </div>
          
        </el-main>
        <el-footer>
          <el-pagination
            layout="prev, pager, next"
            :page-size="4"
            :total="25"
            style="padding-right: 100px">
          </el-pagination>
        </el-footer>
      </el-container>
    </el-container>
    <el-footer class="lowest-footer"></el-footer>
  </el-container>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import SecondaryNav from "./components/SecondaryNav.vue";
import ProductCard from "./components/ProductCard.vue";
import SideBar from "./components/SideBar";

export default {
  name: "App",
  components: {
    NavBar,
    SecondaryNav,
    ProductCard,
    SideBar,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          name: 'Laptop 1',
          price: 799.99,
          rating: 4.8,
          image_url: 'https://images.unsplash.com/photo-1541807084-5c52b6b3adef?ixid=MnwxMjA3fDB8MHxzZWFyY2h8N3x8bGFwdG9wfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 2,
          name: 'Laptop 2',
          price: 849.99,
          rating: 4,
          image_url: 'https://images.unsplash.com/photo-1593642634524-b40b5baae6bb?ixid=MnwxMjA3fDF8MHxzZWFyY2h8OHx8bGFwdG9wfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 3,
          name: 'Laptop 3',
          price: 499.99,
          rating: 4.7,
          image_url: 'https://images.unsplash.com/photo-1575024357670-2b5164f470c3?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MjV8fGxhcHRvcHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 4,
          name: 'Laptop 4',
          price: 999.99,
          rating: 3.9,
          image_url: 'https://images.unsplash.com/photo-1588872657578-7efd1f1555ed?ixid=MnwxMjA3fDB8MHxzZWFyY2h8NjN8fGxhcHRvcHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 5,
          name: 'Laptop 5',
          price: 749.99,
          rating: 4.4,
          image_url: 'https://images.unsplash.com/photo-1593642632823-8f785ba67e45?ixid=MnwxMjA3fDB8MHxzZWFyY2h8NDR8fGxhcHRvcHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 6,
          name: 'Laptop 6',
          price: 749.99,
          rating: 4.2,
          image_url: 'https://images.unsplash.com/photo-1615750185825-fc85c6aba18d?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTc2fHxsYXB0b3B8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 7,
          name: 'Laptop 7',
          price: 599.99,
          rating: 3.5,
          image_url: 'https://images.unsplash.com/photo-1587614297882-0954a02d57f7?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTc5fHxsYXB0b3B8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        },
        {
          id: 8,
          name: 'Laptop 8',
          price: 1099.99,
          rating: 4.5,
          image_url: 'https://images.unsplash.com/photo-1565906624603-eae91627707b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MjY1fHxsYXB0b3B8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60'
        }
      ]
    }
  }
};

// class Product {
//   constructor(id, name, price, image_url, rating) {
//     this.id = id;
//     this.name = name;
//     this.price = price;
//     this.image_url = image_url;
//     this.rating = rating;
//   }
// }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.el-main {
  display: flex;
  flex-flow: row wrap;
}
.el-header {
  padding: 0;
}
.el-container {
  display: flex;
}

.lowest-footer {
  background-color: black;
  position:relative;
  bottom: 0;
  width:100%;
  height:50px;   /* Height of the footer */
}
.el-pagination {
  float: right;
}
</style>
