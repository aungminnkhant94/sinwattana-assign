<template>
      <main class="wrapper">

        <div class="card-container">
          <div class="card">
            <div class="card-title">
              {{ product.product }}
            </div>
            <div class="card-body">
              <img :src="product.img" alt="">
              <form>
                <div class="row">
                  <div class="cell">
                    <label>Type:</label>
                  </div>
                  <div class="cell">
                    <em>{{ product.type }}</em>
                  </div>
                </div>
                <div class="row">
                  <div class="cell">
                    <label>Price:</label>
                  </div>
                  <div class="cell">
                    $4.82
                  </div>
                </div>
                <div class="row">
                  <div class="cell">
                    <label>Quantity:</label>
                  </div>
                  <div class="cell">
                    <input type="number" value="0">
                  </div>
                </div>
              </form>
            </div>
            <div class="card-footer">
              <button class="btn btn-light">Add to cart</button>
            </div>
          </div>

          
        </div>
      </main>

</template>

<script>
export default {
  props: ['product', 'index', 'addToCart'],
  data () {
    return {
      quantity: 0
    }
  }
}
</script>

<style scoped>
  img{
    width: 170px;
    height: 170px;
  }
</style>
