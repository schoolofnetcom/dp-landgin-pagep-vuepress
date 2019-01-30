<template>
<form>
    <header>Baixe sua cópia do e-book</header>

    <input type="text" placeholder="Seu nome"/>
    <input type="text" placeholder="Seu email"/>
    <label>
        <input type="checkbox"> Eu aceito receber emails promocionais e entendo que posso me descadastrar quando quiser.
    </label>
    <btn type="submit">Baixar e-book</btn>
</form>
</template>

<script>
import btn from './btn';

export default {
    components: {
        btn
    }
}
</script>


<style lang="css" scoped>
    * {
        box-sizing: border-box;
        font: inherit;
    }
    form {
        border: 3px solid #f26c4f;
        padding: 20px;
        border-radius: 5px;
    }
    input[type="text"], label {
        display: block;
        margin-bottom: 10px;
    }
    input[type="text"] {
        border: 3px solid #e1e1e1;
        padding: 10px;
        width: 100%;
    }
    header {
        font-weight: bold;
        background: #f26c4f;
        color: white;
        padding: 20px;
        margin: -20px -20px 20px -20px;
    }
</style>
