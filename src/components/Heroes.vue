<template>
  <div class="hero">
    <h1>DC Heroes {{heroLength}}</h1>
    <input type="text" v-model="newHero">
    <button @click="addHero">Add Hero</button>
    <ul>
      <li v-for="(hero, index) in heroes" v-bind:key="hero">
          <div>{{hero.name}}</div>
          <span @click="delHero(index)">X</span>    
      </li>
    </ul>
  
    
  </div>
  
</template>

<script>
export default {
  name: 'Heroes',
  data(){
    return{
      newHero:'',
      heroes:[
      
      ]
     
    }
  },
  methods:{
    addHero(){
      if(this.newHero !== ''){
          this.heroes.push({name : this.newHero})
          this.newHero =''
      } 
    },
    
     delHero(index){
        this.heroes = this.heroes.filter((h, i) => {
          return i != index
         
         
        })
        
  } 
  },
  computed:{
    heroLength(){
      return this.heroes.length
    }
  }
 

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.hero{
  background-color:#90d0e4;
  width: 400px;
  margin: auto;
  text-align: center;
  padding: 10px 0 30px 0;
  margin-top: 10px;
}

.hero h1{
  font-size: 32px;
 
}

input{
  padding: 5px 10px;
  width: 60%;
}

button{
  padding: 5px 10px;
  
}

ul li{
  display: flex;
  justify-content: space-between;
  padding: 0 10px;
  width: 300px;
  line-height: 30px;
  list-style: none;
  font-size: 20px;
  background-color:#90dff7;
  border-bottom: 1px solid rgb(235, 232, 232);
  
}

ul li:nth-of-type(even){
  background-color:#90d0e4;
}

li span{
  cursor: pointer;
 
}

</style>
