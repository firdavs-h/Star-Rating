<template>
  <div class="hello">
  <!-- pass existing rating as prop here -->
    <star-rating :existingRating="0"/>  
    
  </div>
</template>

<script>
import StarRating from './StarRating.vue'

export default {
  name: 'HelloWorld',
 
  components: {
    StarRating
  }
}
</script>

<style >

</style>
