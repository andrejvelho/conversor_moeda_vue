<template>
<div class="footer">
    <div class="footer-area">
        <div>
            <img src="../../assets/andrevelho.png" alt="Logo André Velho" />
        </div>
        <div>
             <a href="https://github.com/andrejvelho" target="_blank">GitHub @andrejvelho</a>
        </div>
    </div>
    <p>
        Orgulhosamente criado durante o curso<br/>
        <a href="https://www.youtube.com/watch?v=tIEa3MRBpI0">Criando um conversor de moedas com VUE JS - S02E10</a>
    </p>
</div>
</template>

<script>
export default {

}
</script>

<style>
.footer {
    background: var(--primary);
    border-top: 2px solid var(--primary);
    padding-left: 16px;
    padding-right: 16px;
    padding-top: 32px;
    padding-bottom: 32px;
    color: var(--white);
    text-align: center;
    @media (max-width: 800px) {
        margin-bottom: 50px;
    }
}

.footer-area {
    display: flex;
    border-bottom: 1px solid #D4D8E0;
    justify-content: space-around;
}

a {
    color: #fff;
}
</style>