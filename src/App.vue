<template>
    <NavBarComponent v-bind:logo="logo_burger" v-bind:alt="app_name" />
    <router-view/>
    <FooterComponent />
</template>

<script>
    import NavBarComponent from './components/NavBar'
    import FooterComponent from './components/Footer'

    export default {
        components: {
            NavBarComponent,
            FooterComponent
        },

        data: function() {
            return {
                logo_burger: '/img/logo.png',
                app_name: 'Make Your Burger'
            }
        }
    }
</script>

<style lang="scss">
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    #app {
        font-family: Helvetica, Arial, sans-serif;
    }

    .main-container {
        margin: 50px;
        min-height: 250px;
    }

    h1 {
        color: #222;
        font-size: 42px;
        margin-bottom: 30px;
        text-align: center;
    }
</style>
