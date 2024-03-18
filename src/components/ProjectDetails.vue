<template>
    <div class="details">
        <div class="details__name">
    {{ project.name }}
        </div>
        <div class="details__description" v-html="project.description">
    
        </div>
        <div class="carousel">
            <button @click="prevIMG" class="carousel__prevButton">&lt;</button>
            <button @click="nextIMG" class="carousel__nextButton">&gt;</button>
            <div class="carousel__images">
                <img :src="image"/>
            </div>
            
            <ul class="carousel__navlinks">
                <input type="radio"  v-for="points,index in project.img" v-model="selectedImg" :value="index"  name="images" :key="index" />
            </ul>
        </div>
    </div>
    </template>


    <script>
    export default{
        name:"ProjectDetails",
        props:{
            project:Object,
        },
        data(){
            return{
                selectedImg: 0
            }
        },
        methods:{
            prevIMG(){
                console.log(this.project.img.length)
                if(this.selectedImg == 0){
                    this.selectedImg = this.project.img.length
                }
                this.selectedImg--
            },
            nextIMG(){
                if(this.selectedImg >= this.project.img.length-1){
                    this.selectedImg = 0
                    return
                }
                this.selectedImg++
            }
        },
        computed:{
            image(){
                return this.project.img.filter((elem, index) => index == this.selectedImg)
            },
            
        }
    }
    </script>

    <style scoped>
    .details{
        margin-top: 200px;
        max-width: var(--max-width);
        margin-inline: auto;
        display: flex;
        align-items: center;
        flex-direction: column;}

    .details__name{
        width: 660px;
        font-family: "DM Serif Display";
        font-size: 50px;
        line-height: 125%;
        letter-spacing: 0.02em;
        color: #292f36; 
    }
    .details__description{
        margin-top: 11px;
        font-family: 'Jost';
        font-size: 22px;
        width: 660px;
        line-height: 150%;
        letter-spacing: 0.01em;
        color: #4d5053;
    }
    .carousel{
        display: flex;
        margin-top: 100px;
        position: relative;
        flex-direction: column;
        align-items: center;
    }

    .carousel__nextButton, 
    .carousel__prevButton{
        position: absolute;
        height: 30%;
        top: 35%;
        border: none;
        width: 50px;
        background-color: #C4C4C4;
        font-size: 25px;
        color: white;
        mix-blend-mode: overlay;
        cursor: pointer;
    }
    .carousel__prevButton{
        left:0;    
    }
    .carousel__nextButton{
        right:0;
    }
    .carousel__images {
        display: flex;
        flex-direction: row;
        width:fit-content;
        justify-content: center;
        align-items: flex-start;
    }
    .carousel__images img{
        object-fit: cover;
    }
    .carousel__navlinks{
        margin-top: 25px;
        display: flex;
        gap: 25px;
    }
    .carousel__navlinks input{
        cursor: pointer;
    }
</style>