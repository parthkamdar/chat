<template>
  <div id="app">
    <div v-if="start_flag">
    <div class="topbox-container">
      <div v-if="checkTime()">
        <h3>Hello !</h3>
        <p>Welcome to Omega Support.</br>
          Start a new Conversation below</br>
        </p>
      </div>
      <div v-else>
        <img src="./assets/moon.png"/>
        <p> The team will respond to your query </br> after 10am IST</p>
      </div>
    </div>

    <div class="displaybox-container">
      <div class="image-row">
        <img src="./assets/Asset1.png"/>
        <img src="./assets/Asset2.png"/>
        <img src="./assets/Asset3.png"/>
      </div>
      <p>The team typically replies in a few hours</p>
      <button v-if="checkTime()" @click="changeFlag()">{{ start }}</button>
      <button v-else>{{ sleep }}</button>
    </div>
  </div>
  <div v-else>
    <topbox></topbox>
    <inputbox></inputbox>
  </div>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      start_flag: true,
      hour: null,
      start: "Start a Converstion",
      sleep: "Contact us after 10am IST",
    }
  },
    methods:{
      changeFlag(){
        this.start_flag = false;
      },
      checkTime(){
        var t = new Date();
        this.hour = t.getHours();
        if(this.hour > 20 || this.hour < 10){
          return false;
        }
        return true;
      }
    }
  }
</script>

<style>
body{
  margin:0px !important;
  width: 100%;
  height: 100vh;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 350px;
  height: 600px;
  display: block;
  margin: auto;
  margin-top:50px;
  background: white;
  border-radius: 10px;
  box-shadow: 5px 70px 25px 2px #ccc;
}
#app > div {
  height: 100%;
  width: 100%;
}
.topbox-container{
  width: 100%;
  height:40%;
  background: url(./assets/top-background.png) no-repeat;
  background-size: cover;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  display: block;
}
.topbox-container h3{
  text-align: center;
  color: white;
  font-size: 2em;
  margin:  0px;
  margin-top: 8%;
  display: inline-block;
}
.topbox-container p{
  text-align: center;
  color: white;
}
.topbox-container img{
  width: 100px;
  margin-top: 10%;
}
.displaybox-container{
  width: 100%;
  background: white;
  border-radius: 10px;
  display: block;
}
.image-row{
  margin-top: 20%;
}
.image-row img{
  width: 10%;
  display: inline-flex;
}
.displaybox-container p{
  margin-top: 10%;
}
.displaybox-container button{
  margin-top:20%;
  width: 60%;
  height: 50px;
  border: none;
  background: #116f8a;
  border-radius: 5px;
  color:white;
}
button:focus{
  outline: none;
}

/* Media Queries */
/*
  ##Device = Desktops
  ##Screen = 1281px to higher resolution desktops
*/

@media (min-width: 1281px) {

  /* //CSS */

}

/*
  ##Device = Laptops, Desktops
  ##Screen = B/w 1025px to 1280px
*/

@media (min-width: 1025px) and (max-width: 1280px) {

  /* //CSS */

}

/*
  ##Device = Tablets, Ipads (portrait)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) {

  /* //CSS */

}

/*
  ##Device = Tablets, Ipads (landscape)
  ##Screen = B/w 768px to 1024px
*/

@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape) {

  /* //CSS */

}

/*
  ##Device = Low Resolution Tablets, Mobiles (Landscape)
  ##Screen = B/w 481px to 767px
*/

@media (min-width: 481px) and (max-width: 767px) {

  /* //CSS */

}

/*
  ##Device = Most of the Smartphones Mobiles (Portrait)
  ##Screen = B/w 320px to 479px
*/

@media (min-width: 320px) and (max-width: 480px) {

  /* //CSS */

}
</style>
