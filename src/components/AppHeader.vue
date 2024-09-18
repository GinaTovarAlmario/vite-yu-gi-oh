<script>
export default {
    data(){
        return{

        }
    }
}
</script>
<template>
    <header>
        <div class="logo">
            <img class="img-logo" src="../assets/img/yu-gi-oh-logo.png" alt="logo">
            <h1>
                Yu-Gi-Oh Api
            </h1>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header{
    height: 120px;
    background-color: white;
    .logo{
        height: 120px;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        margin-left: 10px;
        gap: 10px;
        font-size: 2rem;
        img{
            height: 50px;
        }

    }
}
</style>