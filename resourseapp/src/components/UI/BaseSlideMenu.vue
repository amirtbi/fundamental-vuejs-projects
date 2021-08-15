<template>
    <div class="mobile-menu__container" :class="toggleMenu">
        <ul>
            <li v-for="link in links" :key="link">
                <a href="#">
                <slot :item="link"></slot>

                </a>
            </li>
        </ul>
        <base-button mode="action">
            <span>close</span>
        </base-button>
    </div>
</template>

<script>
export default {
    props:["links"],
    data(){
        return{
            menuIsClicked:false,
        }
    },
    methods:{
        closeSlideMenu(){
            this.menuIsClicked = !this.menuIsClicked;
        }
    },
    computed:{
        toggleMenu(){
            return{
                closeMenu:this.menuIsClicked
            }

        }
    },

    provide(){
        return{

            closeMobileMenu:this.closeSlideMenu
        }
    }
}
</script>

<style scoped>
div.mobile-menu__container{
    background-color: rgb(12, 12, 82);
    height: 100vh;
    position: fixed;
    left: 0;
    top: 0;
    width:300px;
    z-index: 1000;
    transition: transform 1s;
  

}
ul{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0;
    margin: 2rem auto;
    list-style-type: none;
}
ul li{
    padding: 1.2rem;
    color: white;
    font-family:inherit;

}
ul li a{
    color: white;
}
li a:hover{
    color: rgb(0, 144, 240);
}
button{
    position:absolute;
    right:2px;
    top:0;

}
.closeMenu{
    transform: translateX(-500px);
}

</style>