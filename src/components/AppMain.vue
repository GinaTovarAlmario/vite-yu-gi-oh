<script>
import MainMessage from "./MainMessage.vue";
import CardList from "./Cardlist.vue";
export default {
    data(){
        return{
            
        }
    },
    components:{
        MainMessage,
        CardList
    }
}
</script>

<template>
    <main>
        <h2>
        main
        </h2>
        <MainMessage />
        <CardList/>
    </main>
 
</template>

<style lang="scss" scoped>
main{
    background-color: #d48f3b;
}

</style>