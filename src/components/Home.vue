<template>
  <div class="row">
    <aside class="col-sm-3">
      <div class="card card-filter">
        <article class="card-group-item">
          <header class="card-header">
            <a class="" aria-expanded="true" href="#" data-toggle="collapse" data-target="#collapse22">
              <i class="icon-action fa fa-chevron-down"></i>
              <h6 class="title">By Category</h6>
            </a>
            </header>
              <div style="" class="filter-content collapse show" id="collapse22">
                <div class="card-body">
                    <ul class="list-unstyled list-lg">
                      <li v-for="category in categories" v-bind:key="category.name">
                        <a href="javascript:" @click.prevent="categoryClick(category)">{{ category.name }}<span class="float-right badge badge-light round">{{ category.products.length }}</span> </a>
                      </li>
                    </ul>  
                </div> <!-- card-body.// -->
              </div> <!-- collapse .// -->
          </article> <!-- card-group-item.// -->
      </div>

    </aside>
    <main class="col-sm-9">
      <ul class="list-group">
        <Product v-for="product in category.products" v-bind:key="product.name"></Product>
      </ul>    
    </main>
  </div>
</template>


<script>
import Product from './Product.vue'

export default {
  name: 'Home',
  data: function() {
    return {
      'categories': [
        {
          'name': 'fruits',
          'products': [
            {'name': 'banana'},
            {'name': 'orange'}
          ]
        }, 
        {
          'name': 'computers',
          'products': [
            {'name': 'xps15'},
            {'name': 'alienware17'},
            {'name': 'macbook13'}
          ]
        }
      ]
    }
  },
  methods: {
    categoryClick(category) {
      this.category = category;
    }
  },
  created: function() {
    this.category = this.categories[0];
  },
  components: {
    Product
  }
}
</script>