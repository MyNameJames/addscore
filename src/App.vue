<template>
  <div class="clone">
    <!-- <div class="cosnt" >
  <h1 style="left: 15px; color: #fff;"></h1>
  <div class="on">
  <div class="bee" v-for="( player, index ) in sortedPlayers" :key="index">
    <div class="rank">
      <h5>Rank:</h5>
      <h1>{{ player.rank }}</h1>
    </div>
    <div class="box">
      <h5 style="left: 15px">Group:</h5>
      <h1 style="left: 15px">{{ player.text }}</h1>
    </div>
    <div class="score">
      <h5>Score</h5>
      <h1>{{ player.score }}</h1>
    </div>
  </div>
  </div>
</div> -->
 
    <div class="container" >
      <div class="option-card" v-for="item in arr" :value="item.id">
        <label class="option_item" >
          <div class="increase" @click="increase(item.id)">↑<br>Up</div>
          <h4>{{ item.text }}</h4>
          <h1>{{ item.score }}</h1>
          <h2>คะแนน</h2>
          <div class="decrease" @click="decrease(item.id)">Down<br>↓</div>
        </label>
      </div>
    </div>
  </div>
     
  </template>
  
  
  <script>
  
  export default {
    name:'App',

    data() {
    return {
      list: [
        { id:1, text:"กลุ่ม 1", score:0 },
        { id:2, text:"กลุ่ม 2", score:0 },
        { id:3, text:"กลุ่ม 3", score:0 },
        { id:4, text:"กลุ่ม 4", score:0 },
        { id:5, text:"กลุ่ม 5", score:0 },
        { id:6, text:"กลุ่ม 6", score:0 },
        { id:7, text:"กลุ่ม 7", score:0 },
        { id:8, text:"กลุ่ม 8", score:0 },
        { id:9, text:"กลุ่ม 9", score:0 },
        { id:10, text:"กลุ่ม 10", score:0 },
        { id:11, text:"กลุ่ม 11", score:0 },
        { id:12, text:"กลุ่ม 12", score:0 },
        { id:13, text:"กลุ่ม 13", score:0 },
        { id:14, text:"กลุ่ม 14", score:0 },
        { id:15, text:"กลุ่ม 15", score:0 },
        { id:16, text:"กลุ่ม 16", score:0 },
        { id:17, text:"กลุ่ม 17", score:0 },
        { id:18, text:"กลุ่ม 18", score:0 },
        { id:19, text:"กลุ่ม 19", score:0 },
        { id:20, text:"กลุ่ม 20", score:0 },
        { id:21, text:"กลุ่ม 21", score:0 },
        { id:22, text:"กลุ่ม 22", score:0 },
      ],
    }
  },
      methods: {
      updateList(updatedList) {
        this.list = updatedList
         },
         increase(id) {
           this.list.find(item => item.id === id).score++
           this.$emit('update-list', this.list)
         },
         decrease(id) {
           this.list.find(item => item.id === id).score--
           this.$emit('update-list', this.list)
         },
      
    },
    computed: {
    sortedPlayers() {
      const sortedPlayers = this.list.sort((a, b) => b.score - a.score);
      sortedPlayers.forEach((list, index) => {
        list.rank = index + 1;
      });
      return sortedPlayers;
    },
    arr() {
       return this.list.sort((a, b) => a.id - b.id);
    }
  }, 
  }
  
  </script>
  
  
  <style scoped>
  
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@400;600&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Kanit',sans-serif;
}
.clone {
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color:#ffc300;
  
}
.cosnt {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #003566;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
  
}
  
.on {
  margin: 35px;
  height: 800px;
  width: 900px;
  overflow-y: scroll;
  scroll-margin-block: 20px;
  margin: 0 0 40px 0;
}

.on::-webkit-scrollbar{
    display: none;
  }
.bee {
  display: flex;
  justify-content: center;
  border-bottom: #fff solid 2px;
  width: 430px;
  padding: 1.4rem 0 1rem 0;
  margin: 10px auto;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
}
.box1 {
  width: 450px;
  height: 45px;
  margin: 15px;
}
.rank1 {
  width: 100px;
  height: 45px;
  margin: 15px;
}

.score1 {
  width: 110px;
  height: 45px;
  margin: 15px;

}
.box {
  width: 450px;
  height: 75px;
  color:  #000;
}
.rank {
  width: 100px;
  height: 75px;
  border-right: #d2d0d0 solid 1px;
  text-align: center;
  color: #000;

}

.score {
  width: 110px;
  height: 75px;
  margin-left: 15px;
  text-align: center;
  color:  #000;
}


.container {
  margin: 5px;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
  align-items: center;
  width: 1200px;
  /* overflow-y: scroll; */
}

.container::-webkit-scrollbar{
    display: none;
  }

.option-card {
  margin: 10px;
}
.container .option_item {
  width: 100%;
  height: 100%;
  background: #fff;
  border-radius: 5px;
  text-align: center;
  padding: 58px 40px;
  cursor: pointer;
  color: #585c68;
  display: block;
  border: 5px solid transparent;
  position: relative;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
}
.increase {
  /* background:#2f6690; */
  padding: 10px 40px;
  margin: -58px -45px 10px -45px;
  cursor: pointer;
  border-bottom: solid 1px;
  border-color:  #d2d0d0;
}

.decrease {
  /* background: red; */
  border-radius: 5px;
  padding: 10px 40px;
  margin: 10px -45px -65px -45px;
  cursor: pointer;
  border-top: solid 1px;
  border-color:  #d2d0d0;
}
  


  </style>
  
  