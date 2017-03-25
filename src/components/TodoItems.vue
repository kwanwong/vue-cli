<template>
    <div>
        <h3>{{ title }}<small v-show="total" class="pull-right">{{ remaining }} / {{ total }}</small></h3>
        <pre v-show="!total">暂无数据</pre>
        <ul class="list-group">
            <li v-for="(todo, index) in items" :class="{'completed': todo.completed}" class="list-group-item list-group-item-success">
                <button @click="completeTodo(todo)" :class="['btn', 'btn-xs', todo.completed ? 'btn-success' : 'btn-primary']">{{ statusText(todo) }}</button>
                {{ todo.title }}
                <button @click="deleteTodo(index)" class="btn btn-xs btn-warning pull-right">删除</button>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: '',
        props: ['items', 'title'],
        computed: {
            remaining: function(){
                return this.items.filter(function(item){
                    return !item.completed;
                }).length;
            },
            total: function(){
                return this.items.length;
            }
        },
        methods: {
            deleteTodo: function(item){
                this.items.splice(item, 1);
            },
            completeTodo: function(item){
                item.completed = !item.completed;
            },
            statusText: function(item){
                return item.completed ? '完成' : '待办';
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
    h3{
        text-align:left;
    }
    .list-group-item{
        text-align:left;
    }
</style>
