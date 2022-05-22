<template>
    <div>
        <div
            v-for="product in products"
            :key="product.id"
        >
            <InstrumentoEnLista
                :id='product.id'
                :name='product.instrumento'
                :marca='product.marca'
                :modelo='product.modelo'
                :imagen='product.imagen'
                :precio='product.precio'
                :costoEnvio='product.costoEnvio'
                :cantidadVendida='product.cantidadVendida'
                :descripcion='product.descripcion'
            />
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import InstrumentoEnLista from "@/components/InstrumentoEnLista.vue";

    export default {
        name: "ProductsView",
        components: {
            InstrumentoEnLista
        },
        data(){
            return{
                products: null
            }
        },
        mounted(){
            axios.get('http://localhost:5000/api/instrumentos')
            .then(res=> this.products = res.data)
            .catch(e=>console.log(e))
        }
    }
</script>