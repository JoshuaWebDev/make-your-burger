<template>
    <div id ="nav">
        <router-link to="/" id="logo-url">
            <img v-bind:src="logo" v-bind:alt="alt" id="logo" />
        </router-link>
        <router-link to="/">Home</router-link>
        <router-link to="/pedidos">Pedidos</router-link>
    </div>
</template>

<script>
    export default {
        name: 'NavBarComponent',
        props: ["logo", "alt"]
    }
</script>

<style lang="scss" scoped>
    #nav {
        align-items: center;
        background-color: #222;
        border-bottom: 4px solid #111;
        display: flex;
        justify-content: flex-end;
        padding: 15px 50px;
    }

    #nav #logo-url {
        margin: auto;
        margin-left: 0;
    }

    #logo {
        height: 40px;
        width: 40px;
    }

    #nav a {
        color: #fcba03;
        text-decoration: none;
        margin: 12px;
        transition: .5s;
    }

    #nav a:hover {
        color: #fff;
    }
</style>

