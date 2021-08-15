<template>
    <div class="backdrop" @click="hideModal">
    </div>
    <dialog open>
        <div class="title-container">
        <slot name="header">
            <h1>{{title}}</h1>
        </slot>

        </div>
        <div class="description-container">
            <slot name=description></slot>
        </div>
        <div class="button-container">
            <base-button mode="alert" @click="hideModal">
                okay
            </base-button>
           
        </div>
    </dialog>

</template>
<script>
export default {
    inject:["hideModal"],
    props:["title"],
    data(){
        return{
          
        }
    },

}
</script>
<style scoped>
div.backdrop{
    position: fixed;
    top:0;
    height: 100vh;
    width:100vw;
    left:0;
    z-index:5;
    background:rgba(0, 0, 0, 0.8);
}
dialog{
    position:fixed;
    top:10%;
    margin:auto;
    z-index:10;
    width:700px;
    background-color: white;
    border-radius: 5px;
    padding:0;
    border:none;

}
div.description-container{
    display: flex;
    flex-direction: column;
    padding: 10px;
    width:100%
}
div.button-container{
    display: flex;
    flex-direction: row;
    padding: 10px;
    width:100%
}
div.button-container{
    justify-content: space-between;
}
div.title-container{
    display: flex;
    flex-direction: row;
    width:100%;
    padding:10px;
    background-color: rgb(62, 0, 65);
    
    border-bottom: 1px solid black;
    
}
div.title-container h1{
    color:white;
     font-family: "Roboto", sans-serif;;
}
</style>


