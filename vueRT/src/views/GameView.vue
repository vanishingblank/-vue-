<script>
export default {
    data(){
        return {
            boardX : 0,
            boardY : 300,
        }
        

    },
    methods:{
        keyonRL(event){
            if(event.key=='ArrowLeft'){
                if(this.boardX>0){
                    this.boardX-=20 ;
                }
                
            }else if(event.key=='ArrowRight'){
                if(this.boardX<1540)
                {this.boardX+=20;}
            }; 
            
        },
        keyonUD(event){
            if(event.key=='ArrowUp'){
                if(this.boardY>154)
                {this.boardY-=20;}
            }else if(event.key=='ArrowDown'){
                if(this.boardY<700)
                {this.boardY+=20;}
            }
        }
    },
    mounted() {  
        document.addEventListener('keydown', this.keyonRL);  
        document.addEventListener('keydown', this.keyonUD);  
    },  
    beforeUnmount() {  
        document.removeEventListener('keydown', this.keyonRL);  
        document.removeEventListener('keydown', this.keyonUD);  
    },  
};
//Vue.createApp(App).mount("#block");
</script>

<template>
    <main>
        <h1>Just one game</h1>
        <div id="block">
            <div class="board" :style="{left:boardX+'px',top:boardY+'px'}"></div>
        </div>
    </main>
</template>

<style>
.block {  
    position: relative;  
    height: 500px; 
    width: 100%;  
}  
.board{
    position: absolute;
    width:100px;
    height:100px;
    left:0;
    bottom:0;
    background-color:red;
}
</style>