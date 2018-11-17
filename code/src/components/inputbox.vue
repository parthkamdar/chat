<template>
    <div class="chatbox-container" id="chatbox-container">
      <form v-on:submit.prevent>
        <input type="text" v-model="msginput" placeholder="Type Here !!"/>
        <div class="inner" id="chatbox">
        <label for="fileinput"><img src="../assets/attachment.png"/></label>
        <input type="file" name="fileinput" id="fileinput" />
        <button type="button" v-on:click="addchat()" ><img src="../assets/send-button.png"></button>
      </div>
      </form>
      <div class="chatbox">
        <ul>
          <li v-for="inputmsg in inputmsgs">
            <p class="user-input" id="talkbubble">{{ inputmsg }}</p>
            <p class="system-output" id="talkbubble">{{ greeting }}</p>
          </li>
        </ul>
      </div>
    </div>
</template>
<script>
export default{
  name: 'App',
  props: {

  },
  data () {
    return {
      inputmsgs: [],
      greeting: 'Hello, This is a Sample app I cannot do Anything else. Sorry!!',
      msginput: null,
    }
  },
  methods: {
    addchat () {
      if (this.msginput) {
        this.inputmsgs.push(this.msginput)
        this.msginput = ''
      }
    }

  }
}
</script>
<style scoped>
  .chatbox-container{
    width: 100%;
    height: 70%;
    position: relative;
}
  .chatbox{
    width: 94%;
    margin-left:3%;
    margin-right:3%;
    height: 80%;
    overflow: scroll;
  }
  .chatbox::after{
    content: "";
    top: 0;
    border-top: #333333 solid 1px;
  }
  .inner{
    float: right
  }
  ul{
    list-style: none;
    margin: 0px;
    padding: 0px;
  }
  .inner button{
    border: none;
    background: transparent;
  }
  .inner img{
    height: 20px;
    bottom :0;
    margin-right:5px;
  }
  form{
    position: absolute;
    bottom: 20px;
    width: 100%;
  }
  form input[type="text"]{
      border: none;
      border-bottom: 1px solid #000000;
      height: 20px;
      margin-left:10px;
      float:left;
      width: 70%;
  }
  form input[type="file"]{
    display: none;
  }
  form label img{
    height: 20px;
    bottom :0;
    margin-right:5px;
  }
  input:focus,button:focus{
    outline: none;
  }
  .user-input{
    padding: 10px;
    font-size: 0.9em;
    color: #f1f1f1;
    float: left;
    margin-left: 10px;
    background: #053246;
    margin: 5px;
  }
  .system-output{
    padding: 10px;
    font-size: 0.9em;
    color:#333333;
    float: right;
    margin-right: 10px;
    background: #9ed2e8;
    margin: 5px;
  }
  #talkbubble {
    text-align: left;
    display: block;
     width: 200px;
     min-height: 30px;
     position: relative;
     -moz-border-radius: 10px;
     -webkit-border-radius: 10px;
     border-radius: 10px;
   }


</style>
