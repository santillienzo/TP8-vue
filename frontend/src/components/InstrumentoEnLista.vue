<script>
const costoEnvio = 0;

export default {
    name: "InstrumentoEnLista",
    props: {
        id: Number,
        name: String,
        marca: String,
        modelo: String,
        imagen: String,
        precio: String,
        costoEnvio: String,
        cantidadVendida: Number,
        descripcion: String
    }
}
</script>



<template>
        <div class='productContainer'>
            <div class='productImageContainer'>
                <img :src='imagen' alt="" />
            </div>
            <div class='productInfoContainer'>
                <router-link :to='"productos/" + id' class='productTitle'>{{name}}</router-link>
                <p class='productPrice'>$ {{precio}}</p>
                <span class='productShipping free' v-if="costoEnvio === '0'"><img src='../assets/camion.png' alt="" /> Envío gratis a todo el país</span>
                <span class='productShipping non-free' v-else-if="costoEnvio !== '0'">Costo de envío Interior de Argentina: 100</span>
                <span class='productSoldOut'>{{cantidadVendida}} vendidos</span>
            </div>
        </div>
</template>

<style>
.productContainer{
    display: flex;
    width: 90%;
    margin: auto;
    padding: 10px 0;
    border-bottom: 1px solid #ccc;
}

.productInfoContainer{
    padding-left: 20px;
}

.productImageContainer{
    width: 100px;
    height: 100px;
}

.productImageContainer img{
    width: 100%;
}

.productTitle{
    font-weight: 200;
    font-size: 1.2rem;
    cursor: pointer;
    text-decoration: none;
    color: #000;
}
.productTitle:hover{
    text-decoration: underline;
    color: #000;
}

.productPrice{
    font-weight: 400;
    font-size: 1.9rem;
    margin: 0;
}

.productShipping{
    display: flex;
    align-items: center;
}

.productShipping.free{
    color: #39B54A;
}
.productShipping.non-free{
    color: #FF7C25;
}

.productSoldOut{
    font-size: .9rem;
}
</style>

