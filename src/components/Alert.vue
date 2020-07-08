<template>
    <div class="alert alert-success" role="alert">
      <strong>{{ msg }}</strong> 
    </div>
</template>

<script>
export default {
    props: {
        msg: String
    }
}
</script>