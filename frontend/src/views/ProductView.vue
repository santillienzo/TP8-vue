<script>
    import axios from 'axios'

    export default {
        data(){
            return{
                product: null,
                costoEnvio: 0
            }
        },
        mounted(){
            axios.get(`http://localhost:5000/api/instrumentos/${this.$route.params.id}`)
            .then(res=> this.product = res.data[0])
            .catch(e=>console.log(e))
        }
    }
</script>

<template>
    
        <div class='detailProductList'>
            <div class='detailProductSideOne'>
                <div class='detailProductImage'><img :src='product.imagen' alt="" /></div>
                <div class='detailProductDescription'>
                    <h5>Descripción</h5>
                    <p>{{product.descripcion}}</p>
                </div>
            </div>
            <div class='detailProductSideTwo'>
                <span class='productSoldOut'>{{product.cantidadVendida}} vendidos</span>
                <h3 class='productDetailTitle'>{{product.product}}</h3>
                <p class='productPrice'>$ {{product.precio}}</p>
                <div class='brandInfo'>
                    <p>Marca: {{product.marca}}</p>
                    <p>Modelo: {{product.modelo}}</p>
                </div>
                    <span class='productShipping free' v-if="product.costoEnvio === '0'"><img src='../assets/camion.png' alt="" /> Envío gratis a todo el país</span>
                    <span class='productShipping non-free' v-else-if="product.costoEnvio !== '0'">Costo de envío Interior de Argentina: {{product.costoEnvio}}</span>
                <div class='mt-4'>
                    <b-button variant="primary">Agregar al carrito</b-button>
                </div>
            </div>
        </div>
</template>





<style>
.detailProductList{
    display: flex;
}

.detailProductSideOne{
    width: 60%;
}

.detailProductImage{
    display: flex;
    justify-content: center;
}
.detailProductImage img{
    width: 60%;
}

.detailProductSideTwo{
    width: 40%;
    border-left: 1px solid #ccc;
    padding: 15px;
}

.brandInfo{
    margin: 15px 0;
}

.brandInfo p{
    margin: 0;
}

.productDetailTitle{
    font-weight: 400;
    font-size: 1.5rem;
}
</style>