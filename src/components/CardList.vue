<script>
import CardListItem from "./CardListItem.vue";
export default {
    data(){
        return{
            
        }
    },
    props:{
        cards:{
            type:Array,
            required:true
        }
    },
    components:{
        CardListItem,
    },
}
</script>

<template> 
    <div class="container">
        <section>
            <div class="row">
                <CardListItem 
                    v-for="cardItem in cards" :key="cardItem.id"
                    :card="cardItem"
                />
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
section{
    background-color: white;
    padding: 50px;

    .row{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: center;
        gap: 10px;
    }
}

</style>