<script>
import CardListItem from "./CardListItem.vue";
import axios from 'axios';
export default {
    data(){
        return{
            cardList:[],
            apiUrl:'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=100',
            
        }
    },
    methods:{
        getCards(){
            axios.get(this.apiUrl)
            .then((response) => {
                console.log(response.data.data);
                this.cardList = response.data.data;
            })
            .catch(function (error) {
                console.log(error);
            });
        },
    },
    components:{
        CardListItem
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <div class="container">
        <section>
            <div class="row">
                <CardListItem v-for="cardItem in cardList" :key="cardItem.id"
                    :cardObject="cardItem"
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