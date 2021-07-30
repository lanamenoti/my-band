<template>
   <p class="header__text">{{text}}</p> 
</template>

<script>

export default {
    name: "Frase",
    props: ['text']
}

</script>

<style>
    .header__text {
        color: #e2e2e2;
        font-size: 14px;
        font-style: italic;
        margin: 8px;
        font-weight: 700;
    }
</style>