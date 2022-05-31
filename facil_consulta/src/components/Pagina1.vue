<template>
    <div class="container box">
        <div class="row">
            <div class="title">
                <h1>Sobre o profissional</h1>
                <h4>Dados do profissional</h4>
            </div>
            <div class="col w-50">
                <form @submit.prevent="submit">
                    <div class="form-group col-md-12">
                        <label for="nomeCompleto">Nome completo*</label>
                        <input 
                            type="text" 
                            name="name"
                            v-model.trim="$v.name.$model"
                            :class="{'is-invalid': $v.name.$error}" 
                            class="form-control form-control-sm" 
                            id="nomeCompleto" 
                            placeholder="  Digite o nome completo"
                        >
                    </div>
                    
                    <div class="form-group col-md-8">
                        <label for="nCPF">CPF*</label>
                        <input
                            type="text" 
                            name="cpf"
                            v-model.trim="$v.cpf.$model"
                            :class="{'is-invalid': $v.cpf.$error}"
                            class="form-control form-control-sm" 
                            id="nCPF" 
                            placeholder="  Digite um CPF"
                        >
                    </div>
                   
                    <div class="form-group col-md-8">
                        <label for="nCelular">Número do celular*</label>
                        <input
                            type="text" 
                            name="celular" 
                            v-model.trim="$v.celular.$model"
                            :class="{'is-invalid': $v.celular.$error}"
                            class="form-control form-control-sm" 
                            id="nCelular" 
                            placeholder="  (00)0 0000-0000"
                         >
                    </div>
                
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label for="Estado">Estado*</label>
                            <select id="inputState" class="form-control form-control-sm">
                                <option selected>Selecione</option>
                                <option>...</option>
                                <option>...</option>
                                <option>...</option>
                            </select>
                           <span class="iconArrow1"><b-icon icon="arrow-down-short" aria-hidden="true"></b-icon></span>
                        </div>

                        <div class="form-group col-md-6">
                            <label for="Cidade">Cidade*</label>
                            <select id="inputCity" class="form-control form-control-sm">
                                <option selected>Selecione</option>
                                <option>...</option>
                                <option>...</option>
                                <option>...</option>
                            </select>
                            <span class="iconArrow2"><b-icon icon="arrow-down-short" aria-hidden="true"></b-icon></span>
                        </div>
                    </div>
                    <br>  
                </form> <!-- Fim do formulário -->
                    <div class="barProgress line">
                        <span>1 de 2</span>
                    </div>
                    
                    <button type="submit" class="btnProximo">PRÓXIMO</button>
            </div>  <!-- col w-50 -->

            <div class="col w-25 h-25">
                <img src="../assets/desktop-pagina-1.png" alt="Imagem da Pagina 1" class="image">
            </div> <!-- col w-25 h-25 -->
        </div> <!-- row -->
    </div> <!-- container -->
</template>

<script>
    import Pagina2 from './Pagina2.vue'
    import { required, minLength, maxLength } from 'vuelidate/lib/validators';

    export default {
        name: 'Pagina1',
        components: {
            Pagina2
        },
        data() {
            return {
                name: '',
                cpf: '',
                celular: '',
            }
        },
        validations: {
            name: {
                required,
                minLength: minLength(3),
                maxLength: maxLength(48)
            },
            cpf: {
                required,
                minLength: minLength(11),
            },
            celular: {
                required,
                minLength: minLength(11),
            }
        },
        methods: {
            submit() {
                this.$v.$touch();
            }
        }
    }
</script>

<style scoped>

    .box{
        width: 50%;
        height: 530px;
        background-color: #f9f9f9;
        border-radius: 10px;
        box-shadow: 0px 4px 8px 2px rgba(0,0,0,0.2);;
        position: relative;
        top: 0;
        left: 5%;
        transform: translate(-10%, 5%);
    }

    .title h1{
        width: 100%;
        font-size: 2.4rem;
        color: #483698;
        margin-left: 6%;
        margin-top: 5%;
        margin-bottom: 5%;
        font-family: 'Comfortaa', cursive;
    }

    .title h4{
        width: 100%;
        font-size: 1.4rem;
        font-weight: 600;
        color: #282828;
        margin-left: 6%;
        margin-top: 3%;
        margin-bottom: 3%;
    }

    form label{ 
        font-size: .8rem;
        margin-bottom: 2%;
    }

    .form-row{
        display: flex;
    }

    .form-group{
        margin-left: 12%;
    }

    input, select{
        border: 1px solid #483698;
        margin-bottom: 4%;
        cursor: pointer;
    }

    .form-group span {
        position: relative;
    }

    .form-group .iconArrow1{
        position: absolute;
        bottom: 102px;
        left: 180px;
        padding: 10px 10px;
    }

    .form-group .iconArrow2{
        position: absolute;
        bottom: 102px;
        left: 375px;
        padding: 10px 10px;
        cursor: pointer;
    }

    .barProgress{
        width: 100%;
        height: 5%;
        border: none;
        color: #fff;
        margin-left: 12%;
        margin-bottom: 4%;
        font-size: .8rem;
        background: #f9f9f9;
        position: relative;
    }

    .barProgress::before{
        content: "";
        border-radius: 2px;
        position: absolute;
        height: 100%;
        left: 0;
        top: 0;
        background-color: #483698;
    }

    .line::before{
       width: 33%;
    }

    .line span{
        position: absolute;
        left: 80%;
        top: 40%;
        transform: translate(40%, -50%);
        color: #483698;
        font-size: 1rem;
        font-weight: 600;
        font-family: 'Comfortaa', cursive;
    }

    .btnProximo{
        width:100%;
        height: 7%;
        border: none;
        border-radius: 8px;
        color: #fff;
        margin-left: 12%;
        margin-bottom: 2%;
        font-size: .9rem;
        font-family: 'Comfortaa', cursive;
        background-color: #483698;
        cursor: pointer;
    }

    .image{
        width: 96%;
        position: relative;
        top: 10%;
        left: 25%;
        transform: translate(-18%, 5%);
    }
</style>