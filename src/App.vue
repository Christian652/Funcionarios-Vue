<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-white shadow-lg py-3" style="border-bottom: 2px solid rgb(43,43,43);">
      <div class="d-block m-auto">
        <img src="./assets/logo.png" style="height: 90px" class="img-fluid" alt="">
      </div>        
    </nav>

    <div class="container mt-4">

      <Alert :msg="message" v-if="visible" />

      <Create @created="insert($event)"/>

      <hr>

      <div class="row justify-content-center">
        <div class="col-md-6 mb-3" v-for="funcionario in orderFuncionarios" :key="funcionario.nome">
          <Funcionario :funcionario="funcionario" />
        </div>
      </div>      
    </div>
  </div>
</template>

<script>
import Funcionario from './components/Funcionario'
import Create from './components/Create'
import Alert from './components/Alert'
import _ from 'lodash'

export default {
  name: 'App',
  components: {
    Funcionario,
    Create,
    Alert
  },
  data() {
    return {
      funcionarios: [
        {
          nome: "Christian",
          cargo: "Ceo Da Central Web e Dev Node.js"
        }
      ],
      message: "",
      visible: false
    }
  },
  computed: {
    orderFuncionarios() {
      return _.orderBy(this.funcionarios, ['nome'])
    }
  },
  methods: {
    insert(event) {
      var funcionario = event.funcionario

      this.message = "Funcionario Inserido Com Sucesso!"
      this.visible = true

      setTimeout(() => {
        this.visible = false
        this.message = ""
      }, 3000)

      this.funcionarios.push(funcionario)
    }
  }
}
</script>

<style>

  body {
    background: rgb(210,210,210);
  }

</style>
