<script>
import CardListItem from "./CardListItem.vue";
import MainLoader from "./MainLoader.vue";
import axios from 'axios';
import {store} from "../store.js";
export default {
    data(){
        return{
            apiUrl:'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=100',
            store,
            
        }
    },
    methods:{
        getCards(){
            axios.get(this.apiUrl)
            .then((response) => {
                console.log(response.data.data);
                store.cardList = response.data.data;
                store.loaded= true;
            })
            .catch(function (error) {
                console.log(error);
            });
        },
    },
    components:{
        CardListItem,
        MainLoader
    },
    created(){
        setTimeout(this.getCards,2000);
    }
}
</script>

<template> 
    <MainLoader v-if="!store.loaded"/>
    <div class="container" v-else>
        <section>
            <div class="row">
                <CardListItem v-for="cardItem in store.cardList" :key="cardItem.id"
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