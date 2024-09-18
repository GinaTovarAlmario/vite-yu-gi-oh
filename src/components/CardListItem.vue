<script>
export default {
    data(){
        return{
            
        }
    }
}
</script>

<template>
    <div div class="col" v-for="n in 15">
        <div class="card">
            <img class="card-img" src="" alt="">
            <p class="card-txt">text</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.col{
    width: calc(100% / 5 - 10px);

    .card{
        height: 100px;
        border: 1px solid black;
        background-color: cyan;
    }


}

</style>