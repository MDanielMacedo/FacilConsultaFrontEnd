<template>
    <div id="btnProximo">
        <button-counter>PRÓXIMO</button-counter>
    </div>
</template>

<script>

    Vue.component('button-counter', {
    data: function () {
        return {
        count: 0
        }
    },
    template: '<button v-on:click="count++">Você clicou em mim {{ count }} vezes.</button>'
    })
    new Vue({ el: '#btnProximo' })

</script>