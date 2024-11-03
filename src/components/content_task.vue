<script>
export default{
  data(){
    return{
      task:'',
      listTask:[],
      pic:''
    }
  },
  
  methods:{
    addTask(){
      this.listTask.push(this.task);
      this.task=''; //очистка поля после добавления
    },

    sortTask(){
        this.listTask.sort();
    },
    del(){
        
        //delete this.listTask[this.pic]; //-остается пустой элемент в массиве
        // this.listTask.pop(); //-не подхоит, удалает последний элемент
        this.listTask.splice(this.pic, 1);
        //alert(this.listTask);
        //alert(this.pic);
        
    }


  }
}
</script>


<template>
      
    <div class="content">
      <div class="container">
        <p>Тут добавляй задачи:</p>
        <input type="text" class="i-t" v-model="task">
        <input type="button" @click="addTask" class="i-t2" value="Добавить" >
        <p> {{ task }}</p>
        
        <p>Тут смотри задачи:</p>
        <div class ="ul-task">
            <ul>
              <li v-for="(i,index) in listTask"> 
                <input type="radio" name="task" :value="index" v-model="pic"> {{i}}
              </li>
              
            </ul>
        </div>
        <div class="cont-bottom">
            <input type="button" class="i-t3" value="Сортировать" @click="sortTask">
            <input type="button" class="i-t3" value="Удалить" @click="del">
        </div>


        
      </div>
    </div>
    
  </template>


<style scoped>



.container{
  width: 70%;
  background-color: antiquewhite;
  border-radius: 10px;
  padding: 25px;
  margin: 70px auto;

  
}

.container p{
  font-size: 25px;
  text-transform: uppercase;
  text-align: center;
  margin-bottom: 15px;
}

.i-t{
  width: 60%;
  height: 35px;
  border: none;
  margin: 10px ;
  margin-right: 15px;
  padding:6px;
  border-radius: 10px;
  }

.i-t2{
  margin: 10px;
  padding:10px;
  border: none;
  border-radius: 10px;
  margin: 10px;
  background-color: rebeccapurple;
  color: #fff;
  font-size: 20px;
  text-transform: uppercase;
}

.i-t2:hover{
    background-color: rgb(154, 101, 207);
    box-shadow: 1px 1px 3px rgb(0, 0, 0); 
}

.ul-task{
    margin-left: 40%;
    
}

.cont-bottom{
  display: flex;
  justify-content: center;
}

.i-t3{
  margin: 10px;
  padding:10px;
  
  border: none;
  border-radius: 10px;
  background-color: rebeccapurple;
  color: #fff;
  font-size: 20px;
  text-transform: uppercase;
}

.i-t3:hover{
    background-color: rgb(154, 101, 207);
    box-shadow: 1px 1px 3px rgb(0, 0, 0); 
}

</style>
