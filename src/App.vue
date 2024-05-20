<template>
  <div id="app">
    <h1>Fazer Cadastro</h1>

    <div>
      <form>
        <label>Nome </label>
        <input type="text" v-model="user.nome" /><br/>

        <label>Email </label>
        <input type="email" v-model="user.email" /><br/>

        <label>Qtd Funcionarios </label>
        <input type="number" v-model="user.qtdFunc" /><br/>        

        <label>Opiniao </label>
        <textarea v-model="opiniao"></textarea><br/>

        <label>Tecnologias</label>    
        <span><input type="checkbox" value="javascript" v-model="tecnologias" />JavaScript</span>
        <span><input type="checkbox" value="css" v-model="tecnologias"/>Css</span>
        <span><input type="checkbox" value="vuejs" v-model="tecnologias"/>VueJS</span><br/>

        <label>Qual tipo de contrataçao</label>
        <select v-model="tipoSelecionado">
          <option v-for="item in tipos" :key="item.id" :value="item.nome"> {{item.nome}} </option>
        </select><br/>

        <label>Qual seu nivel?</label>
        <span><input type="radio" value="basico" v-model="nivel" />Basico</span>
        <span><input type="radio" value="intermediario" v-model="nivel" />Intermediario</span>
        <span><input type="radio" value="avancado" v-model="nivel" />Avançado</span>

      </form>
    </div>

    <hr/>

    <div class="item">
      <h2>Usuario Cadastrado</h2>

      <label>Nome: {{user.nome}}</label><br/>
      <label>Email: {{user.email}}</label><br/>
      <label>Qtd Funcionarios: {{user.qtdFunc}}</label><br/>
      <label>Sua Opiniao: {{opiniao}}</label><br/>
      <label>Tecnologias:</label>
      <ul>
        <li v-for="tech in tecnologias" :key="tech"> {{tech}} </li>
      </ul> <br/>
      <label>Tipo de contrataçao: {{tipoSelecionado}} </label> <br/>
      <label>Nivel atual: {{nivel}} </label>

    </div>

  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      user:{
        nome: '',
        email: '',
        qtdFunc: 0
      },
      opiniao: '',
      tecnologias: [],
      tipos:[
        { id: 1, nome: 'Freelancer' },
        { id: 2, nome: 'CLT'},
        { id: 3, nome: 'PJ'},
        { id: 4, nome: 'Remoto'}
      ],
      tipoSelecionado: 'Freelancer',
      nivel: 'basico'
    }
  }
}
</script>

<style scoped>
  form{
    display: flex;
    flex-direction: column;
  }
</style>