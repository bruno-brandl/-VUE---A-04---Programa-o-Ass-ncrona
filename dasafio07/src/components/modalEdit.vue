<template>
    <div class="information-modal">
        <div class="form-style">
            <h2>Atualizar Filme <i id="close" class="fa fa-window-close" aria-hidden="true"></i>
            </h2>
            <form>
                <input v-model="filme.name" type="text" placeholder="Nome do Filme" />
                <input type="date" placeholder="Ano" />
                <input type="text" placeholder="Genero" />
                <input type="text" placeholder="Sinopse" />
                <input type="text" placeholder="Link trailer" />
                <button @click="editList">Salvar</button>
            </form>
        </div>
    </div>
</template>
<script lang="ts">
import axios from "axios";
import { Vue, Prop, Watch } from "vue-property-decorator";
import { IFilme } from '@/components/types'
export default class MovieList extends Vue {


    private url: 'http://localhost:3000/filmes/';

    public filme: IFilme = {
        name: "",
        ano: null,
        genero: "",
        sinopse: "",
        link: "",
        id: null,
    }

    @Prop() public filmeProp!: IFilme
    // closeModal() {
    //     this.Modal = false
    // }

    @Watch("filmeProp")
    testeWatch() {
        this.filme = this.filmeProp
        console.log(this.filme);
        console.log(this.filmeProp);
    }

    async editList(filme: object) {
        try {
            await axios.put(`/${this.url}`, filme)
        } catch (error) {
            console.log(error)
        }
    }
}
</script>
<style scopeed>
#close {
    margin-left: 212px;
    right: 11px;
    border: none;
    background-color: transparent;
    height: 32px;
    font-size: 19px;
}

#close:hover {
    cursor: pointer;
    transform: translateZ(0px) scale(1.2);
}

.form-style {
    width: 500px;
    padding: 30px;
    flex-direction: column;
    border-radius: 10px;
    background-color: white;
    color: rgb(0, 0, 0);
    position: absolute;
    top: 45%;
    left: 50%;
    right: -50%;
    transform: translate(-50%, -50%);
    box-shadow: 0px 0px 1px 1100px rgba(0, 0, 0, 0.239);

}

h2 {
    background: #4D4D4D;
    font-family: 'Open Sans Condensed', sans-serif;
    color: white;
    font-size: 18px;
    font-weight: 100;
    padding: 20px;
    text-align: center;
    margin: -38px -2px 35px -4px;

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