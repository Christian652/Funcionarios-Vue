<template>
    <div class="row">
        <div class="col-12">
          <div class="card bg-white">
            <div class="card-body">
              <h3>Novo Funcionario!</h3>

              <div>
                <div class="form-group">
                  <input type="text" v-model="nomeField" placeholder="Digite Aqui O Nome do Funcionario" class="form-control">
                </div>

                <div class="form-group">
                  <input type="text" v-model="cargoField" placeholder="Digite Aqui O Cargo do Funcionario" class="form-control">
                </div>

                <button class="btn btn-dark" @click="create">Salvar</button>
              </div>
            </div>
          </div>
        </div>
      </div>
</template>

<script>
export default {
    data() {
        return {      
            nomeField: "",
            cargoField: "",
        }
    },
    methods: {
        create() {
            let nome = this.nomeField;
            let cargo = this.cargoField;

            var funcionario = {
                nome,
                cargo
            }

            this.nomeField = ''
            this.cargoField = ''
         
            this.$emit('created', {
                funcionario
            })
        }
    }
}
</script>