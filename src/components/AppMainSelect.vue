<script>
export default{
    data(){
        return{
            selectedItem:'',

        }
    },
    props:{
        cards:{
            type: Array,
            required:true,
        },
        itemArchetype:{
            type:Array,
            required:true,
        }
    },
    methods:{
        // un metodo per popolare la select
        getInfoArchetype(){
            this.$emit('info-log');
        },
        // un metodo per poter cercare questo specifico archetype
        searchArchetype(word){
            this.$emit('search-info',word);
        },
    },
    created(){
        this.getInfoArchetype();
    }

}
</script>

<template>
    <div class="selection-type">
        <select name="archetype" id="archetype" v-model="selectedItem" @change="searchArchetype(selectedItem)" >
            <option v-for="(singleArchetype,index) in itemArchetype"
            :key="index" :value="singleArchetype.archetype_name">
                {{ singleArchetype.archetype_name }}
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