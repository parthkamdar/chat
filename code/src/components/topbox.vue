<template>
  <div class="topbox-container">
    <div v-if="checkTime()">
      <img src="../assets/left-arrow.png" class="back" @click="refresh_page()"/>
      <h3>Hello !</h3>
      <p>Welcome to Omega Support.</br>
        Start a new Conversation below</br></br>
      <strong>Someone From our Team will Respond Soon.</strong></p>
    </div>
    <div v-else>
      <img src="../assets/left-arrow.png" class="back" @click="refresh_page()"/>
      <img src="../assets/moon.png"/>
      <p> The team will respond to your query at 10am IST</p>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
      hour: null,
    }
  },
  methods: {
    checkTime(){
      var t = new Date();
      this.hour = t.getHours();
      if(this.hour > 20 || this.hour < 10){
        return false;
      }
      return true;
    },
    refresh_page(){
       window.location.reload();
    }
  }
}

</script>

<style scoped>
.back{
  position: absolute;
  top:5px !important;
  left:10px;
  width: 5% !important;
}
.topbox-container{
  width: 100%;
  height:30%;
  background: url(../assets/top-background.png) no-repeat;
  background-size: cover;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  display: block;
  position: relative;
}
.topbox-container h3{
  text-align: center;
  color: white;
  font-size: 1.5em;
  margin:  0px;
  margin-top: 8%;
  display: inline-block;
}
.topbox-container p{
  text-align: center;
  color: white;
  font-size: 0.9em;
}
.topbox-container img{
  width: 100px;
  margin-top: 10%;
}
</style>
