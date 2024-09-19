<script>
export default {
    data(){
        return{
        
        }
    },
    props:{
        card:{
            type: Object,
            required:true,
        }
    }
}
</script>

<template>
    <div div class="col">
        <div class="card">
            <img class="card-img" :src="card.card_images[0].image_url" :alt="card.name ">
            <h4 class="card-name">
                {{ card.name }}
            </h4>
            <p class="card-species">
                {{ card.archetype }}
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.col{
    width: calc(100% / 5 - 10px);

    .card{
        height: 350px;
        border: 1px solid black;
        background-color: #d48f3b;
        overflow: hidden;
        text-align: center;

        h4{
            color: white;
            padding: 10px 0;
        }
        img{
            width:100%;
            height:auto;
        }
    }


}

</style>