<template>
  <v-container>
    <v-row>
      <v-col cols="12" sm="6" class="text-center text-sm-right">
        <v-btn large to="/meetups" class="primary m-a-2">Explore Meetups</v-btn>
      </v-col>
      <v-col cols="12" sm="6" class="text-center text-sm-left">
        <v-btn large to="/meetup/new" class="primary">Organize Meetup</v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-carousel>
          <v-carousel-item v-for="item in items" :key="item.id" v-bind:src="item.imgUrl"
          >
          <div class="title text-center">{{ item.title }}</div>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Main',

  data: () => ({ items: [
    { imgUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/New_york_times_square-terabass.jpg/1280px-New_york_times_square-terabass.jpg', id: '34324343', title: 'Meetup In Newyork' },
    { imgUrl: 'https://live.staticflickr.com/7628/16746636328_96312a3069_b.jpg', id: '324324', title: 'Meetup In Paris' }
  ] })
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.title
  text-transform: uppercase
  background-color: rgba(0,0,0,0.5)
  color: #ffffff
</style>
