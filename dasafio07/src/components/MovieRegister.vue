<template>
    <div>
        <div class="form-style">
            <h2>Cadastre um Filme</h2>
            <form>
                <input v-model="name" type="text" placeholder="Nome do Filme" />
                <input v-model="ano" type="date" placeholder="Ano" />
                <input v-model="genero" type="text" placeholder="Genero" />
                <input v-model="sinopse" type="text" placeholder="Sinopse" />
                <input v-model="link" type="text" placeholder="Link trailer" />
                <input type="submit" value="Cadastrar" @click="postFilms" />
            </form>
        </div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            name: "",
            ano: "",
            genero: "",
            sinopse: "",
            link: ""
        }
    },
    methods: {
        async postFilms() {
            try {
                const newFilmw = { name: this.name }
                await axios.post(`http://localhost:3000/filmes`, newFilmw);
                alert("Filme adicionado com secesso")
                this.$router.push("list")
            } catch (error) {
                alert('erro')
            }
        }
    }
}
</script>
<style scopeed>
.form-style {
    font-family: 'Open Sans Condensed', arial, sans;
    width: 500px;
    padding: 30px;
    background: #FFFFFF;
    margin: 50px auto;
    box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.22);
    -moz-box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.22);
    -webkit-box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.22);

}

h2 {
    background: #4D4D4D;
    font-family: 'Open Sans Condensed', sans-serif;
    color: #797979;
    font-size: 18px;
    font-weight: 100;
    padding: 20px;
    margin: -30px -30px 30px -30px;
}

.form-style input[type="text"],
.form-style input[type="date"],
.form-style input[type="email"] {
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    outline: none;
    display: block;
    width: 100%;
    padding: 7px;
    border: none;
    border-bottom: 1px solid #ddd;
    background: transparent;
    margin-bottom: 10px;
    font: 16px Arial, Helvetica, sans-serif;
    height: 45px;
}

.form-style textarea {
    resize: none;
    overflow: hidden;
}

.form-style input[type="button"],
.form-style input[type="submit"] {
    border: solid 2px black;
    background-color: #ffffff;
    display: inline-block;
    cursor: pointer;
    color: #000000;
    font-family: 'Open Sans Condensed', sans-serif;
    font-size: 14px;
    padding: 8px 18px;
    text-decoration: none;
    text-transform: uppercase;
    border-radius: 9px;

}

.form-style input[type="button"]:hover,
.form-style input[type="submit"]:hover {
    background: linear-gradient(to bottom, #454545 5%, #454545 100%);
    background-color: #454545;
    color: #ffffff;
}
</style>