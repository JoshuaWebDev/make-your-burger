<template>
    <footer id="footer">
        <p>Make Your Burger &copy; 2022</p>
    </footer>
</template>

<script>
    export default {
        name: 'FooterComponent'
    }
</script>

<style lang="scss">
    #footer {
        align-items: center;
        background-color: #222;
        border-top: 4px solid #111;
        bottom: 0;
        color: #fcba03;
        display: flex;
        justify-content: center;
        height: 200px;
        width: 100%;
    }
</style>