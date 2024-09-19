<script>
export default{
    data(){
        return{

        }
    },
    props:{
        cards:{
            type: Array,
            required:true,
        }
    },
    methods:{
        logInfoCard(){
            console.log('sono il figlio');
            this.$emit('info-log');

        }
    }
}
</script>

<template>
    <div class="selection-type">
        <select name="archetype" id="archetype"
        @click="$emit('info-log')"
        >
            <option v-for="cardItem in cards" :key="cardItem.id">
                {{ cardItem.archetype }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
.selection-type{
    height: 80px;
    font-size: 20px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding-left: 50px;
    select{
        width: 150px;
        height: 30px;
    }
}
</style>