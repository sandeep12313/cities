<template>
    <div>
        <h1> {{TitleName}} </h1>
    </div>
    </template>
    <script>
    export default{
        name: 'HeaderTop',
        props:{
            TitleName: String
        }
    }
    </script>
    <style scoped>
    div{
        text-align: center;
        color: #d9d0a1;
        font-family: 'Times New Roman', Times, serif;
        background-color: black;
    }
    </style>