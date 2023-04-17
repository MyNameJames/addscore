<!-- <template >
<div class="container" >
  <div class="option-card" v-for="item in list" :value="item.id">
  <label class="option_item" >
    <div class="increase" @click="increase(item.id)">↑<br>Up</div>
    <h4>{{ item.text }}</h4>
    <h1>{{ item.score }}</h1>
    <h2>คะแนน</h2>
    <div class="decrease" @click="decrease(item.id)">Down<br>↓</div>
  </label>
</div>
</div>

</template>

  
<script>
export default {
  props: {
    list: {
      type: Object,
    }
  },
  methods: {
    
    increase(id) {
      this.list.find(item => item.id === id).score++
      this.$emit('update-list', this.list)
    },
    decrease(id) {
      this.list.find(item => item.id === id).score--
      this.$emit('update-list', this.list)
    }
  },
  compute: {
    arr(){
      this.list.sort((a, b) => a.id - b.id);
      console.log(this.list)
      return this.list
    }
  },
  mounted() {
    this.list.sort((a, b) => a.id - b.id);
  },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@400;600&display=swap');


.container {
  display: flex;
  flex-wrap: nowrap;
  height: 100vh;
  justify-content: flex-start;
  align-items: center;
  /* padding: 10px; */
  max-width: 1400px;
  overflow-x: scroll;
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
.main {
  display: flex; 
  flex-direction: row;
  justify-content: space-around;
  flex-wrap: wrap;
}
.card {
  padding: 1rem;
  margin: 1rem;
  background-color: #fff;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
  max-width: 320px;
  border-radius: 20px;
  border: none;

}
h3 {
  font-size: 25px;
  padding: -15px;
}

.title {
  /* display: flex; */
  align-items: center;
}

.data {
  display: flex;
  flex-direction: column;
  justify-content: center;
}



.card-buttons {
  height: 80%;
  display: flex;
  justify-content: center;
  align-items: center;
  justify-content: space-between;
  padding-top: -15px;
}

.card-buttons h1 {
  padding: 0 30px;
  font-size: 60px;
}

.card-button {
  border: none;
  /* padding: 2px 2px; */
  height: 60px;
  width: 60px;
  border-radius: 10px;
  font-size: 40px;
  font-weight: bold;
  cursor: pointer;
}

.primary {
  background-color: #000;
  color: #fff;
}

.secondary {
  background-color:  #000;
  color: #fff;
}


</style> -->
