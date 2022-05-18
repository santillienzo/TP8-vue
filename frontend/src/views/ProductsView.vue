<template>
    <div>
        <InstrumentoEnLista/>
        <InstrumentoEnLista/>
        <InstrumentoEnLista/>
        <InstrumentoEnLista/>
    </div>
</template>

<script>
    import InstrumentoEnLista from "@/components/InstrumentoEnLista.vue";

    export default {
        name: "ProductsView",
        components: {
            InstrumentoEnLista
        }
    }
</script>