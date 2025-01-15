<script>
import ListJSON from './components/listJSON.vue'

export default {
  components:{ListJSON},
  data() {
    return {
      json: null,
      completed:'Нажми для выбора true или false' // Инициализируем переменную как null
    };
  },
  methods:{
    switchToF(){
      if(this.completed == false){
        this.completed = true
      }else{
        this.completed = false
      }
    }
  },
  async created() {
    // Используем fetch и обрабатываем Promise с помощью async функции
    const response = await fetch('https://jsonplaceholder.typicode.com/todos');
    const jsonValue = await response.json();

    // Присваиваем полученные данные в компонент
    this.json = jsonValue;
    console.log(jsonValue); // Выводим JSON объект в консоль
  }
};
</script>

<template>
  <div>
    <b>completed:</b><br>
    <button @click="switchToF($event.target.completed)">{{completed}}</button>
  </div>
  <ListJSON v-for="(el, index) in json" :el="el" :index="index" :completed="completed"/>
</template>

<style scoped>
  button{
    margin-top: 20px;
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(45,186,130,1) 0%, rgba(70,108,50,1) 59%);
    color:#c0aaaa;
    height: 50px;
    padding: 10px;
  }

  div{
    width: 50px;
    margin-top: 20px;
  }

  b{
    color:black;
  }
</style>
