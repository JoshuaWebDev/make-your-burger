<template>
    <div>
        <small>Componente de mensagem</small>
        <form id="burger-form">
            <div class="input-container">
                <label for="name">Nome do Cliente</label>
                <input type="text" id="name" name="name" v-model="name" placeholder="Digite o seu nome" />
            </div>

            <div class="input-container">
                <label for="bread">Tipo de Pão</label>
                <select id="bread" name="bread" v-model="bread">
                    <option value="">Selecione o tipo de pão</option>
                    <option v-for="bread in breads" v-bind:key="bread.id" v-bind:value="bread.type">
                        {{ bread.type }}
                    </option>
                </select>
            </div>

            <div class="input-container">
                <label for="meat">Tipo de Carne</label>
                <select id="meat" name="meat" v-model="meat">
                    <option value="">Selecione o tipo de carne</option>
                    <option v-for="meat in meatTypes" v-bind:key="meat.id" v-bind:value="meat.type">
                        {{ meat.type }}
                    </option>
                </select>
            </div>

            <div id="optional-container" class="input-container">
                <label id="optional-title" for="optional">Opcionais</label>
                <div class="checkbox-container" v-for="optional in optionalData" v-bind:key="optional.id">
                    <input type="checkbox" name="optionals" v-model="optionals" v-bind:value="optional.type">
                    <span>{{ optional.type }}</span>
                </div>
            </div>

            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu Burger">
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'BurgerForm',

        data: function() {
            return {
                breads: null,
                meatTypes:null,
                optionalData: null,
                name: null,
                bread: null,
                meat: null,
                optionals: [],
                status: "Solicitado",
                message: null
            }
        },

        methods: {
            async getIngredients() {
                const request = await fetch('http://localhost:3000/ingredients')
                const data = await request.json()

                this.breads = data.breads
                this.meatTypes = data.meat
                this.optionalData = data.optionals
            }
        },

        mounted: function() {
            this.getIngredients()
        }
    }
</script>

<style lang="scss" scoped>
    label {
        border-left: 4px solid #FCBA03;
        color: #222;
        font-weight: bold;
        margin-bottom: 15px;
        padding: 5px 10px;
    }

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #burger-form {
        margin: 0 auto;
        max-width: 400px;
    }

    #optional-container {
        flex-direction: row;
        flex-wrap: wrap;
    }

    #optional-title {
        width: 100%;
    }

    .input-container {
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }

    .checkbox-container {
        align-items: flex-start;
        display: flex;
        margin-bottom: 20px;
        width: 50%;

        span, input {
            width: auto;
        }

        span {
            font-weight: bold;
            margin-left: 6px;
        }
    }

    .submit-btn {
        background-color: #222;
        border: 2px solid #222;
        color: #FCBA03;
        cursor: pointer;
        font-size: 16px;
        font-weight: bold;
        margin: 0 auto;
        padding: 10px;
        transition: .5s;

        &:hover {
            background-color: transparent;
            color: #222;
        }
    }
</style>