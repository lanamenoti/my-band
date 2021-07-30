<template>
    <header class="header">
        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <Logo></Logo>
                </div>
                <div class="col-md-6 header__right">
                    <Frase text="escrevi por props"></Frase>
                    <Menu></Menu>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
import Logo from "./Logo.vue"
import Menu from "./Menu.vue"
import Frase from './Frase.vue'

export default {
    name: "Header",
    components: {
        Logo,
        Menu, 
        Frase
    }
}

</script>

<style>
    .header {
        background-color: #000;
        height: 80px;
        width: 100%;
    }

    .header__right {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
    }
</style>