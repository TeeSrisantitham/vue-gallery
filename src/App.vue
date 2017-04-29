<template>
<div class="container-fluid">
    <div class="row">
      <div class="col-md-offset-2 col-md-1">  
        <button type="button" v-on:click="prev()" class="btn btn-info">< prev</button>
      </div>
      <div class="col-md-5">
        <img class="img-center" :src="images[counter]">
      </div>
      <div class="col-md-1">
        <button type="button" v-on:click="next()" class="btn btn-info">next ></button>
      </div>
    </div>
    <div class="row">
        <div class="col-md-2" v-for="(img, index)  in images" v-bind:class="{ active: counter==index  }">
          <img class="img-thumbnail" :src="img" v-on:click="counter=index">
        </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        counter: 0,
        images: [
          'https://images.pexels.com/photos/139575/pexels-photo-139575.jpeg',
          'https://static.pexels.com/photos/94287/pexels-photo-94287.jpeg',
          'https://static.pexels.com/photos/50594/sea-bay-waterfront-beach-50594.jpeg',
          'https://static.pexels.com/photos/392027/pexels-photo-392027.jpeg',
          'https://static.pexels.com/photos/392748/pexels-photo-392748.jpeg',
          'https://static.pexels.com/photos/392779/pexels-photo-392779.jpeg',
          'https://static.pexels.com/photos/396300/pexels-photo-396300.jpeg',
          'https://static.pexels.com/photos/396301/pexels-photo-396301.jpeg',
          'https://static.pexels.com/photos/396237/pexels-photo-396237.jpeg'
        ]
      }
    },
    methods: {
      next () {
        if (this.counter + 1 < this.images.length) {
          this.counter++
        } else {
          this.counter = 0
        }
      },
      prev () {
        if (this.counter - 1 >= 0) {
          this.counter--
        } else {
          this.counter = this.images.length - 1
        }
      }
    }
  }
</script>

<style>
  .img-center {
    width: 100%;
    max-height: 300px;
  }
  .img-thumbnail {
    width: 100%;
    max-height: 121px;
    margin-bottom: 20px;
    cursor: pointer;
  }
    .active .img-thumbnail{
      background-color: red;
    }
  .row {
    margin-bottom: 20px;
  }
  button {
    margin-top: 130px;
  }
</style>
