<template>
    <footer>
        <ul>
            <li v-for="link in mainLinks" :key="link">
                <a href=#>{{link}}</a>
            </li>
        </ul>
    </footer>
</template>


<script>
export default {
    props:["mainLinks"]
}
</script>

<style scoped>
footer{

 
    margin-top: calc(100% - 228px);
    display: flex;
    flex-direction: row;
    width:100vw;
    background-color: rgb(23, 0, 53);
    align-items: center;
    justify-content: center;
}
ul{
    padding:0;
    margin: 0;
    list-style-type: none;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width:100%;
}
li{
    color:white;
    padding:1rem;
    color:white
}
li a{
    color:rgb(139, 139, 139)
}
li a:hover{
    color: white;
}
</style>