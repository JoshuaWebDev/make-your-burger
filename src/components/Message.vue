<template>
    <div class="message-container">
        {{ message }}
    </div>
</template>

<script>
    export default {
        name: "MessageComponent",

        props: {
            message: {
                type: String,
                required: false
            }
        }
    }
</script>

<style lang="scss" scoped>
    .message-container {
        background-color: rgba($color: #9ac2a7, $alpha: .5);
        border: 2px solid #c0e0cd;
        border-radius: 5px;
        color: #042c11;
        font-weight: bold;
        padding: 10px;
        margin: 30px auto;
        max-width: 400px;
    }
</style>