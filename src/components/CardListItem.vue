<script>
export default {
    data(){
        return{
            
        }
    },
    props:{
        cardObject:{
            type: Object,
            required:true,
        }
    }
}
</script>

<template>
    <div div class="col">
        <div class="card">
            <img class="card-img" src="" alt="">
            <h4 class="card-name">
                {{ cardObject.name }}
            </h4>
            <p class="card-species">
                {{ cardObject.archetype }}
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.col{
    width: calc(100% / 5 - 10px);

    .card{
        height: 100px;
        border: 1px solid black;
        background-color: #d48f3b;

        h4{
            color: white;
        }
    }


}

</style>