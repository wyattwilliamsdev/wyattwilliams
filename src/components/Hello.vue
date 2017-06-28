<template>
  <body>
    <div class="parallax-container">
      <div class="parallax">
          <img src="../assets/Orion.jpg"/>
      </div>
    </div>
    <div class = "section black">
      <div class ="row">
        <div class="col s6">
          <h1 class="center-align" style="color:white;">Wyatt Williams</h1>
          <p class="center-align" style="color:white;">Hi, I'm Wyatt Williams. I studied Physics and Astronomy at the University of Nevada Reno.
          I'm currently in the transition of becoming a developer. My past experiences have all been computer science based. From sifting</p>
        </div>
        <div class="col s6">
          <h1 class="center-align" style="color:white;">Reading</h1>
        </div>
      </div>
    </div>
    <div class="parallax-container">
      <div class="parallax">
          <img src="../assets/Moon3.jpg"/>
      </div>
    </div>
    <div class="section white">
      <div class="row">
        <div class="col s12">
          <h1>Experience</h1>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
  var parseString = require('xml2js').parseString
  export default {
    name: 'Hello',
    data () {
      return {}
    },
    created: function () {
      this.$http.get('https://crossorigin.me/https://www.goodreads.com/review/list?v=2&id=68964386&key=cG9KiyzfxG31nxkfLXSvBw').then(function (response) {
        parseString(response.body, function (err, result) {
          console.log(err)
          console.dir(result)
        })
        this.profile = response.data
      })
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.parallax img {
  width: 100%;
}

</style>
