<template>
  <div class="app">
    <form>
      <h4>Создание поста</h4>
      <input v-bind:value="title"
       @input="title =$event.target.value"
        class="input"
         placeholder="Название">
      <input v-bind:value="body"
       @input="body =$event.target.value" 
       type="text" 
       class="input"
        placeholder="Описание">
      <button class="btn" @click="createPost">Создать</button>
    </form>

    <div class="post" v-for="post in posts" v-bind:key="post.id">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
  </div>
    
 
    
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      posts:[
        {id:1, title:'Javascript',   body: 'тело поста'},
        {id:2, title:'Javascript 2', body: 'тело поста 2'},
        {id:3, title:'Javascript 3', body: 'тело поста 3'},
        {id:4, title:'Javascript 4', body: 'тело поста 4'},
      ],
      title:'',
      body:''
   }
  },
  methods:{
    createPost(){
      // const newPost ={
      //   id:Date
      // }
    },
    
  }
  
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;

}
.app{
  padding: 20px;
}
.post{
  padding:15px;
  border: 2px solid teal;
  margin-top: 15px;
}
.input{
  width: 100%;
  border: 2px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.form{
display: flex;
flex-direction: column;
}
.btn{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 2px solid teal;
  border-radius: 10px;
  box-shadow: 3px 3px 3px rgba(0, 128, 128, 0.397);
}
</style>
