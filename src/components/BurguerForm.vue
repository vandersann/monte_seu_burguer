<template>
    <div>
        <Message  :msg="msg" v-show="msg"/>
    </div>
        <div>
            <form id="burguer-form" @submit="createBurguer">
                <div class="input-container">
                    <label for="nome">Nome do cliente:</label>
                    <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite o seu nome">
                </div>
                <div class="input-container">
                    <label for="pao">Escolha o pão:</label>
                    <select name="pao" id="pao" v-model="pao">
                        <option value="">Selecione o seu pão</option>
                        <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">
                            {{ pao.tipo }}
                            </option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="carne">Escolha a carne:</label>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="">Selecione o sua carne</option>
                        <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">
                            {{ carne.tipo }}
                            </option>
                    </select>
                </div>
                <div id="opcionais-container" class="input-container">
                    <label id="opcionais-title" for="opcionais">Escolha os opcionais:</label>
                    <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                        <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo">
                        <span>
                            {{ opcional.tipo }}
                        </span>
                    </div>
                </div>
                <div class="input-container">
                    <input class="submit-btn" type="submit" value="Criar meu burguer">
                </div>
            </form>
        </div>

</template>
<script>
import Message from './Message'

export default {
    name: "BurguerForm",
    components: {
        Message
    },
    data() {
        return {
        paes: null,
        carnes: null,
        opcionaisdata: null,
        nome: null,
        pao: null,
        carne: null,
        opcionais: [],
        msg: null
        }
    },
    methods: {
        async getIngredientes() {
            const req = await fetch("http://localhost:3000/ingredientes");
            const data = await req.json();

            this.paes = data.paes;
            this.carnes = data.carnes;
            this.opcionaisdata = data.opcionais;
        },
        async createBurguer(e) {

            e.preventDefault()

            const data = {
                nome: this.nome,
                carne: this.carne,
                pao: this.pao,
                opicionais: Array.from(this.opcionais),
                status: "Solicitado"
            }

            const dataJson = JSON.stringify(data)

            const req = await fetch("http://localhost:3000/burgers", {
                method: "POST",
                headers: { "Content-Type": "application/json"},
                body: dataJson
            });

            const res = await req.json();

            console.log(res)

            this.msg = `Pedido Nº ${res.id} realizado com sucesso!`;

            setTimeout(() => this.msg = "", 3000);

            this.nome = "";
            this.carne = "";
            this.pao = "";
            this.opcionais = [];
        }
    },
    mounted() {
        this.getIngredientes();
    }
}
</script>
<style scoped>
    #burguer-form {
        width: 420px;
        margin: 0 auto;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        background-color: #fcba03;
    }

    .input-container {
        display: flex;
        flex-direction: column;
        margin-bottom: 1.5rem;
    }

    label {
        font-weight: bold;
        font-size: 1.2rem;
        margin-bottom: .5rem;
        color: #222;
        padding: 5px 5px;
    }

    input, select {
        padding: 1px 10px;
        width: 300px;
    }

    #opcionais-container {
        flex-direction: row;
        flex-wrap:wrap;
        margin-left: 3.8rem;
    }

    #opcionais-title {
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: flex-start;
        width: 50%;
        margin-bottom: 20px;
    }

    .checkbox-container span,
    .checkbox-container input {
        width: auto;
    }

    .checkbox-container span {
        margin-left: 6px;
        font-weight: bold;
    }

    .submit-btn {
        background-color: transparent;
        color: #000;
        width: 200px;
        text-transform: uppercase;
        font-weight: bold;
        border: 2px solid;
        border-radius: 10px;
        padding: .6rem;
        font-size: 1rem;
        margin: 0;
        cursor: pointer;
        transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
    }

    .submit-btn:hover {
        box-shadow: 0 0 40px 40px black inset;
        color: #fff;
    }

</style>