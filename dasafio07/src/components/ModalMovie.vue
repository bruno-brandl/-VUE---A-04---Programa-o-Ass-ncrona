<template>
    <section class="information-modal" v-show="Modal">
        <nav class="navbar-modal">
            <i v-on:click="closeModal" id="close" class="fa fa-window-close" aria-hidden="true"></i>
            <h4>Detalhes do Filme</h4>

        </nav>

        <div class="contain-all-information">
            <div class="informations">
                <div class="information-content">

                    <label>Nome</label>
                    <span>{{ User_Prop.name }}</span>
                    <span></span>
                </div>
                <div class="information-content">
                    <label>ANO</label>
                    <span></span>
                </div>
                <div class="information-content">
                    <label>Nascimento</label>
                    <span></span>
                </div>
            </div>

            <div class="informations">
                <div class="information-content">
                    <label>Genero</label>
                    <span></span>
                </div>
                <div class="information-content">
                    <label>Sinopse</label>
                    <span></span>
                    <p>Link</p>
                    <span></span>
                </div>
            </div>
        </div>
    </section>
</template>
<script lang="ts">
import { PropType } from 'vue'
import axios from "axios";
import { Component, Vue, Prop } from "vue-property-decorator";

export default class MovieList extends Vue {
    @Prop() public User_Prop!: object []
    Modal = true
    filmes = []
    closeModal() {
        if (this.Modal == true) {
            this.Modal = false
        }
    }
}
</script>
<style scoped>
* {
    color: rgb(255, 255, 255);
}

.information-modal {
    width: calc(55% - 158px);
    height: calc(70% - 109px);
    flex-direction: column;
    border-radius: 10px;
    background-color: white;
    position: absolute;
    top: 45%;
    left: 50%;
    right: -50%;
    transform: translate(-50%, -50%);
    box-shadow: 0px 0px 1px 1100px rgba(0, 0, 0, 0.239);
}

.navbar-modal {
    width: 100%;
    height: 45px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.contain-all-information {
    margin: 25px;
    margin-top: 10px;
    padding: 40px;
    display: flex;
    justify-content: space-between;
    border: 2px solid rgba(211, 211, 211, 0.542);
    border-style: dashed;
}

.informations {
    width: 45%;
}

.information-content {
    margin: 15px 0px;
    display: flex;
    flex-direction: column;
}

#close {
    position: absolute;
    right: 11px;
    border: none;
    background-color: transparent;
    height: 32px;
    font-size: 39px;
}

#close:hover {
    cursor: pointer;
    transform: translateZ(0px) scale(1.2);
}

.close {
    width: 21px;
    height: 21px;
    color: rgb(75, 75, 75);
}

span {
    font-weight: bold;
    display: flex;
    align-items: center;
}

label {
    font-size: 14px;
}

.modal-email {
    font-size: 13px;
}
</style> 