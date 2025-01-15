<script>
    export default {
        props:{
            el :{
                type:JSON,
                require:true
            },
            completed:{
                type:String,
                require:true
            }
        }
    };
</script>

<template>
    <div className="listBlock" v-if="el.completed != true && completed != true  || completed == 'Нажми для выбора true или false' ">
        <span><b>userId:</b>{{ el.userId }}</span>
        <span><b>id:</b>{{ el.id }}</span>
        <span><b>title:</b>{{ el.title }}</span>
        <span><b>completed:</b>{{ el.completed }}</span>
    </div>
    <div className="listBlock" v-if="el.completed != false && completed != false">
        <span><b>userId:</b>{{ el.userId }}</span>
        <span><b>id:</b>{{ el.id }}</span>
        <span><b>title:</b>{{ el.title }}</span>
        <span><b>completed:</b>{{ el.completed }}</span>
    </div>
</template>

<style scoped>
    .listBlock{
        height: 100px;
        border: 2px solid #fff;
        margin-top: 20px;
        margin-bottom: 20px;
        padding: 30px 10px;
        text-align: center;
        width:50px;
        background: rgb(2,0,36);
        background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(45,186,130,1) 0%, rgba(70,108,50,1) 59%);
    }

    span{
        display: block;
        margin-top: 5px;
    }

    b{
        color:black;
        margin-right: 5px;
    }
</style>
