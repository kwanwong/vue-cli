<template>
    <form action="" @submit.prevent="addTodo(newTodo)">
        <div class="form-group">
            <input type="text" class="form-control" placeholder="请输入日程" v-model="newTodo.title">
        </div>
        <div class="form-group">
            <button class="btn btn-primary btn-block">添加日程</button>
        </div>
    </form>
</template>

<script>
    export default {
        name: '',
        props: ['items'],
        data: function(){
            return {
                newTodo: {id:null, title:'', completed:false}
            }
        },
        methods: {
            addTodo: function(item){
                if(item.title){
                    this.items.push(item);
                    this.newTodo = {id: null, title: '', completed:false};
                }
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .row{
        padding: 10px 0 0 0;
    }
    .completed{
        color: #ff7246;
        text-decoration: line-through;
    }
</style>
