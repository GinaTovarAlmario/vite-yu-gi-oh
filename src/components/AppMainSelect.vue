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
        },
        itemArchetype:{
            type:Array,
            required:true,
        }
    },
    methods:{
        getInfoArchetype(){
            this.$emit('info-log');
        }
    },
    created(){
        this.getInfoArchetype();
    }

}
</script>

<template>
    <div class="selection-type">
        <select name="archetype" id="archetype">
            <option v-for="(singleArchetype,index) in itemArchetype" :key="index">
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