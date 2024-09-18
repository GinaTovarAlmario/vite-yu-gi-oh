<script>
import CardListItem from "./CardListItem.vue";
import axios from 'axios';
export default {
    data(){
        return{
            cardList:[],
            apiUrl:'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
            
        }
    },
    methods:{
        getCards(){
            axios.get(this.apiUrl)
            .then((response) => {
                console.log(response.data.data);
                // this.cardList = response;
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
    <section>
        <div class="row">
            <CardListItem/>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section{
    background-color: magenta;

    .row{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: center;
        gap: 10px;
    }
}

</style>