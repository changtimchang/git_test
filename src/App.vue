<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니=false" >닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
    
  </div>
   
  
  
  
  <div> 
    <img src="./assets/1.jpg" class="room-img" @click="모달창열렸니=true">
    <h4 >{{products[0]}} 원룸 </h4>
    <P>{{ price[0]}} 만원</P>
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}} </span>
  </div>
  <div>
    <img src="./assets/2.jpg" class="room-img">
    <h4>{{products[1]}} 원룸 </h4>
    <P>{{ price[1] }} 만원</P>
    <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}} </span>
  </div>
  <div>
    <img src="./assets/3.jpg" class="room-img">
    <h4>{{products[2]}} 원룸 </h4>
    <P>{{ price[2] }} 만원</P>
    <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}} </span>
  </div>
  


</template>

<script>






export default {
  name: 'App',
  data(){                    //데이터 바인딩 : 데이터 보관함
    return {
      모달창열렸니 : false,
      신고수 : [0,0,0],
      price : [80,70,60],      
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      메뉴들 : ['Home','Shop', 'About']
    }
  },
  //  methods : {         //함수쓰려면 만들어야함.
  //    increase(){
  //      this.신고수++;
      
  //    }
  //  },

  components: {
   
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu > a{
  color: white;
  padding: 10px;
}

.room-img{
  width : 100%;
  margin-top:40px;
}

.black-bg {
  width:100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
  
}

.white-bg {
  width:100%; 
  background: white;
  border-radius: 8px;
  padding : 20px;
}



</style>
