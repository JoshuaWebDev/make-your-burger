<template>
    <BannerComponent />
    <div class="main-container">
        <h1>Monte seu burger:</h1>
        <BurgerForm />
    </div>
</template>

<script>
    import BannerComponent from '../components/Banner.vue'
    import BurgerForm from '../components/BurgerForm.vue'

    export default {
        name: 'HomeView',

        components: {
            BannerComponent,
            BurgerForm
        }
    }
</script>
