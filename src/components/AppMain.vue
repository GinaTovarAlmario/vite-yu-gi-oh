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
        }
    },
    methods:{
        getCards(){
            axios.get(this.apiUrl,{
                params:{
                    num: 20,
                    offset:50,
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
            axios.get(apiUrlArchetype)
            .then((response) => {
                console.log(response.data.data);
                this.cardList = response.data.data;
            })
            .catch(function (error) {
                console.log(error);
             });
        },
        parentInfoLog(){
            console.log('evento info-log è dal padre');

        },

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
        @info-log="parentInfoLog"
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