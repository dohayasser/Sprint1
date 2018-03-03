<template>
    <div class="container">
          <table class="table table-striped table-borders">
            <thead>
<th> Name </th>
<th> Price </th>
<th> Created At </th>
<th> Updated At </th>
<th> Seller Name </th>
            </thead>
            <tbody>
            <tr v-for="product_alias in Product" >
            <td> {{ product_alias.id}}</td>
            <td> {{ product_alias.name}}</td>
            <td> {{ product_alias.price}}</td>
            <td> {{ product_alias.createdAt}}</td>
            <td> {{ product_alias.updatedA}}</td>

            </tr>
            </tbody>
          </table>
    </div>
</template>
<script>
import axios from 'axios'

export default{
  data () {
    return {
      Product: []
    }
  },
  mounted () {
    axios.get('http://localhost:3000/api/product/getProducts')
      .then((response) => {
        console.log(response.data)
        this.Product = response.data
      })
  .catch((error) => {
    console.log(error)
  })
  }}

</script>
<style>

</style>
