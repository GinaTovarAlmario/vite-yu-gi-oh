<script>
export default{
    data(){
        return{

        }
    }
}
</script>

<template>
    <div class="loader-wrapper">
        <div class="loader"></div>
    </div>
</template>
<style lang="scss">
.loader-wrapper{
    display: flex;
    justify-content: center;
    padding: 50px 0;

    .loader {
        width: 200px;
        aspect-ratio: 1;
        border-radius: 50%;
        border: 8px solid lightblue;
        border-right-color: orange;
        animation: l2 1s infinite linear;
    }
}
@keyframes l2 {to{transform: rotate(1turn)}}

</style>