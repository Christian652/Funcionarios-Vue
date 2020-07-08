<template>

    <div class="card border-white mb-3">
        <div class="card-header bg-white text-center text-dark">
            <h3>{{ funcionario.nome }}</h3>
        </div>

        <div class="card-body text-center">
            <strong>{{ funcionario.cargo }}</strong>
        </div>
    </div>

</template>

<script>
export default {
    props: {
        funcionario: {
            nome: String,
            cargo: String
        }
    }
}
</script>