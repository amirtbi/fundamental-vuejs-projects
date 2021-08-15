<template>
    <button  :type="type" :class="mode">
        <slot></slot>
    </button>
</template>


<script>
export default {
    props:["type","mode"],
    // inject:["closeMobileMenu"]
}
</script>

<style  scoped>
button{
  
  border-radius: 2px;
  border: none;
  outline: none;
  padding: 10px 20px;
  font-family: inherit;
  font-size: 1.2rem;
  font-weight:bold;
  cursor: pointer;
  font-family: 'Karla', sans-serif;
 
}

.action{
    background-color:rgb(0, 1, 68);
    color:white;
 
}
button.action:hover{
    background-color: rgb(23, 2, 143);
}
.flat{
    background-color:white;
    color:black;
    border-radius: 0;
    border:none;

}
.alert{
    background-color: rgb(90, 0, 75);
    color: white;
}
.alert:hover{
    background-color: rgb(141, 1, 83);
}
button.flat:hover{
    background-color: gray;
    
}
 
</style>