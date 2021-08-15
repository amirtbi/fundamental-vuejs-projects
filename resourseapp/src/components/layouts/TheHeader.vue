<template>
    <header>
        <h1>{{title}}</h1>
    </header>
</template>

<script>
export default {
    props:["title"]
}
</script>

<style scoped>
header{
    display: flex;
    flex-direction: row;
    width:100vw;
    justify-content: center;
    align-items: center;
    background-color: rgb(134, 0, 45);
}
header h1{
    color:white;
    font-family: inherit;
    font-size: 3rem;


}
</style>>