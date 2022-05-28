<template>
    <div id="main-banner">
        <h1>Make Your Burger</h1>
    </div>
</template>

<script>
    export default {
        name: 'BannerComponent'
    }
</script>

<style lang="scss" scoped>
    #main-banner {
        align-items: center;
        background-image: url('../assets/burger.jpg');
        background-position: 0 -250px;
        background-size: cover;
        display: flex;
        height: 500px;
        justify-content: flex-start; 

        h1 {
            background-color: #222;
            color: #fff;
            font-size: 3em;
            padding: 20px 40px;
            text-align: center;
        }
    }
</style>