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
          The images on this site are taken both from a normal telescope and the photometry photo of Orion was taken with the Great Basin Observatory.
        </p>
        </div>
        <div class="col s6">
          <h1 class="center-align" style="color:white;">Reading</h1>
          <div class="readinglist">
              <ol>
                <li v-for=""
              </ol>
          </div>
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
        console.log(response[0]['reviews'][0]['review'][1].body)
        debugger
      })
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media only screen and (max-width : 950px) {
  .parallax img {
    max-height: 130%; /* or a little bit higher */
  }
}

@media only screen and (min-width: 933px) {
  .parallax img {
    max-height: 170%; /* or higher percentages. It's up to your taste */
  }
}

</style>
