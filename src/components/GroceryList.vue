<template>
  <div class="grocery">
    <h1 class="title">Grocery List</h1>
    <div class="form">
        <input @keyup.enter="addItems" v-model="inputValue" class="input" type="text" >
        <i @click="deleteItems" class="bi bi-pencil-fill"></i>
    </div>
    <div class="allIttems">
        <h2 @click="onItemClick(item)"  v-for="(item, index) of completeList" :key="index" class="item" :class="{'item--done': doneList.includes(item)}">{{ item }}</h2>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            inputValue:'',
            completeList:[], 
            doneList:[], 
        }
    },

    methods:{
        addItems(){
            const newItem = "- " + this.inputValue;
            this.completeList.push(newItem);
            this.inputValue = "";
        },

        deleteItems(){
            this.completeList = [];
        },

        onItemClick(item){
            this.doneList.push(item)
        }
    }
}
</script>

<style scoped>
.grocery{
width: 600px;
display: flex;
flex-direction: column;
margin-top: 50px;
margin-bottom: 50px;
min-height: 90vh;
background: white;
box-shadow: 10px 14px 15px 13px black;
border-radius: 10px;
align-items: center;
background-color: #e5e5f7;
opacity: 0.8;
background-image: linear-gradient(#1c1c24 1px, transparent 1px), linear-gradient(to right, #1c1c24 1px, #e5e5f7 1px);
background-size: 20px 20px;
}

.title{
margin-top: 25px;
font-size: 3.5rem;
margin-top: 15px;
color: rgb(7, 73, 70);
}

.form{
margin-top: 25px;
text-align: center;
display: flex;
justify-content: space-between;
}

.bi{
font-size: 1.5rem;
color:rgb(7, 73, 70) ;
}

.input{
font-family: inherit;
outline: 0;
border: 0;
border-bottom: 3px solid rgb(7, 73, 70);
width: 90%;
font-size: 1.5rem;
background-color: #e5e5f7;
}

.allItems{
margin-left: 50px;
margin-right: 15px;
margin-top: 15px;
margin-bottom: 10px;
font-size: 2rem;
}

.item{
    color: rgb(15, 15, 15);
}

.item--done{
    text-decoration-line: line-through;
}

</style>