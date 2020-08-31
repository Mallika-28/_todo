<template>
  <v-app>
    
      <!-- <div class="d-flex align-center">
        <v-img src="https://artside.com.ua/home/catalog/product13628/shutterstock_465762650.jpg"/>
      </div> -->
      <!-- <div :style="{'background-image':'url(https://artside.com.ua/home/catalog/product13628/shutterstock_465762650.jpg)'}"> -->
      <!-- </div> -->

      <v-hoover class="shadow">
        <div class="img" style="background-image:url(https://artside.com.ua/home/catalog/product13628/shutterstock_465762650.jpg)">
        <div class="v-card shaped">
          <div class="v-card-title" ><h1>TODO LIST</h1></div>
          <v-card-text>
            <input class="input" v-model="newToDo" placeholder="Enter a task...">

            <!-- Button to add items in our todo list  -->
            <!-- On click is an event handler which will listen to Dom events and run the add function when triggered  -->
            <button class="button" v-on:click="add()"><span>Add </span></button>
            <div class="image" style="background-image:url('https://i.pinimg.com/originals/0e/de/fc/0edefc77d5080abd571625d14e35926f.png')">
            </div>
          </v-card-text>
          <center><hr size="1000"></center><br><br><br>
          <button class="button" > <span><a href="https://calendar.google.com/calendar/r">Schedule</a></span> </button><br><br>
          <button class="button"><span><a href="https://mallika-28.github.io/jump-game/"> Refresh yourself! </a> </span></button>
        </div>
      <!-- </v-hoover> -->
      <div class="v-card shaped2">
          <div class="v-card-title" ><h2>YOUR TASKS</h2></div>
          <!-- <v-card-text> -->
            <ul>
              <li v-for='(todo,id) in existingToDo' :key="id">
                <span>
                  {{id+1}}: {{todo.text}}
                  </span>
                <button class="delete-button btn"><i class="fa-fa-trash delete-button" @click="deleteToDo(id)">D</i></button>
              </li>
            </ul>
          <!-- </v-card-text> -->
        </div>
        </div>
      </v-hoover>

      <footer class="new_footer_area bg_color">
            <div class="new_footer_top">
              <div class="footer_bg">
                <div class="footer_bg_two"></div>
                </div>
            </div>
        </footer>

  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'app',
  //Data is a function that is going to return an object
  data(){
    return{
      // msg: 'We are the best'
      //todos are going to be the array of objects
      newToDo: '',
      existingToDo:[
        {text:'Build a restraunt app', id:0},
        {text:'Sleep', id:1},
        {text:'Hydrate yourself', id:2}
      ]
    }
  },
    //Ading 
    methods:{
      add(){
        this.existingToDo.push({
          text: this.newToDo,
          id: new Date().valueOf()
        }),
        // After user input something in input form and add it. They can refresha nd add a new thing
        this.newToDo='';
      },
      deleteToDo(id){
        this.existingToDo.splice(id,1)
      }
    }
  }

  
</script>

<style scoped>
*{
  box-sizing: border-box;
  margin:0;
  padding: 0;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.button, input {
  border-radius: 4px;
  background-color: #00b33c ;
  border: none;
  color: #FFFFFF;
  text-align: center;
  font-size: 18px;
  padding: 10px;
  width: 50%;
  transition: all 0.5s;
  cursor: pointer;
  margin: 5px;
}
input{
  background-color: white;
  color: black;
  width: 95%;
  border: 1px solid black;
}

.button span, .button a {
  text-decoration: none;
  color: white;
  cursor: pointer;
  display: inline-block;
  position: relative;
  transition: 0.5s;
}


.button span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -20px;
  transition: 0.5s;
}

.button:hover span {
  padding-right: 25px;
}

.button:hover span:after {
  opacity: 1;
  right: 0;
}

hr{
  align-content: center;
  text-align: center;
  width: 70%;
  color: black;
  font-weight: 300px;

}

.btn{
  /* background-color: black; */
  /* color: #FFFFFF; */
  width: 30px;
  padding: 3px;
  align-content: center;
  font-size: 20px;
}

.btn a{
  text-decoration: none;
}

.shaped, .shaped2{
  height: 100%;
  width: 27%;
  padding: 10px;
  /* border: 1px solid black; */
  left: 25%;
  border: 1px solid;
  padding: 15px;
  text-align: center;
  top: 12%;
}

.shaped2{
  left: 55%;
  top: -70%;
  height: 120%;
}

.v-card{
  background: linear-gradient(to bottom, #ffffff 0%, #ccffdc 100%);
}

.v-card-title{
  background-color: #006622;
}

.shadow{
  box-shadow: 5px 10px 18px #707096;
  /* background-color:  #2929a3; */
  height:65%;
}
.shaped, .shaped2{
  background-color: white;
  box-shadow: 5px 10px 18px #707096;
}

.shaped h1, h2{
  text-align: center;
  align-content: center;
  color: white;
}

ul{
  list-style-type: none;
  text-align: left;
  padding: 20px;
}

.img{
  width: 100%;
  height: 100%; 
  background: url("https://artside.com.ua/home/catalog/product13628/shutterstock_465762650.jpg");
    background-repeat: no-repeat;
    background-size: cover;
}

.new_footer_top .footer_bg .footer_bg_two {
    background: url("https://1.bp.blogspot.com/-hjgfxUW1o1g/Xck--XOdlxI/AAAAAAAAT_4/JWYFJl83usgRFMvRfoKkSDGd--_Sv04UQCLcBGAsYHQ/s1600/cyclist.gif") no-repeat center center;
    width: 88px;
    height: 100px;
  background-size:100%;
    bottom: 0;
    left: 38%;
    position: absolute;
    -webkit-animation: myfirst 30s linear infinite;
    animation: myfirst 30s linear infinite;
    position: fixed;
}

@keyframes myfirst {
  0% {
    left: -25%;
  }
  100% {
    left: 100%;
  }
}

</style>