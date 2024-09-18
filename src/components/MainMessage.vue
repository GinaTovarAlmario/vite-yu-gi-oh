<script>
import {store} from "../store.js";
export default {
    data(){
        return{
            store,
            
        }
    }
}
</script>

<template>
    <section class="container">
        <div class="message">
            <p>Found {{store.cardList.length}} cards</p>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section{
    background-color: #212429;
    height: 100px;
    color: white;
    font-size: 1.5rem;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding-left: 20px;
}

</style>