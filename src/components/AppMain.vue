<script>
import MainMessage from "./MainMessage.vue";
import CardList from "./CardList.vue";
import MainLoader from "./MainLoader.vue";
import axios from 'axios';
import AppMainSelect from "./AppMainSelect.vue";

export default {
    data(){
        return{
            cardList:[],
            apiUrl:'https://db.ygoprodeck.com/api/v7/cardinfo.php',
            loaded: false,
            apiUrlArchetype:'https://db.ygoprodeck.com/api/v7/archetypes.php',
            listArchetype:[],
        }
    },
    methods:{
        getCards(filterWord = null){
            axios.get(this.apiUrl,{
                params:{
                    num: 35,
                    offset:0,
                    archetype: filterWord,

                }
            })
            .then((response) => {
                console.log(response.data.data);
                this.cardList = response.data.data;
                this.loaded= true;
            })
            .catch(function (error) {
                console.log(error);
             });
        },
        getCardsArchetypes(){
            axios.get(this.apiUrlArchetype)
            .then((response) => {
                console.log(response.data);
                this.listArchetype=response.data

            })
            .catch(function (error) {
                console.log(error);
             });
        },
         // un metodo in risposta alla chiamata fatta da appMainsearch
         showInfoArchetype(information){
            this.getCards(information);
        }

    },
    components:{
        MainMessage,
        CardList,
        MainLoader,
        AppMainSelect
    },
    created(){
        setTimeout(this.getCards,1000);
    }
}
</script>

<template>
    <main>
        <!-- mi aspetto un evento personalizzato da AppMainselect -->
        <AppMainSelect :cards="cardList"
        :itemArchetype ="listArchetype"
        @info-log="getCardsArchetypes"
        @search-info ="showInfoArchetype"

        />
        <MainMessage :cards="cardList"/>
        <MainLoader v-if="!loaded"/>
        <CardList :cards="cardList" v-else/>
    </main>
 
</template>

<style lang="scss" scoped>
main{
    background-color: #d48f3b;
}

</style>