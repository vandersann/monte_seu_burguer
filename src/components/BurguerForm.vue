<template>
    <div>
        <p>Componente de mensagem</p>
    </div>
        <form id="burger-form">
            <div class="input-container">
                <label for="name">Nome do cliente:</label>
                <input type="text" id="nome" name="name" v-model="name" placeholder="Digite o seu nome">
            </div>
            <div class="input-container">
                <label for="pao">Escolha o pão:</label>
                <select name="pao" id="pao" v-model="pao">
                    <option value="">Selecione o seu pão</option>
                    <option value="integral">Integral</option>
                </select>
            </div>
            <div class="input-container">
                <label for="carne">Esolha a carne:</label>
                <select name="carne" id="carne" v-model="carne">
                    <option value="">Selecione o sua carne</option>
                    <option value="fraldinha">Fraldinha</option>
                </select>
            </div>
            <div class="input-container">
                <label for="pao">Esolha os opcionais:</label>
                <div class="checkbox-container">
                    <input type="checkbox" name="opcionais" v-model="opcionais" value="peperoni">
                    <span>Peperoni</span>
                </div>
            </div>
            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu burguer!">
            </div>
        </form>

</template>
<script>
export default {
    name: "BurguerForm"
}
</script>
<style scoped>

</style>