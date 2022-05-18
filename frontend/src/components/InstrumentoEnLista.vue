<script>
const costoEnvio = 0;

export default {
    name: "InstrumentoEnLista",
    data: ()=>({
        costoEnvio: '0'
    })
}
</script>



<template>
        <div class='productContainer'>
            <div class='productImageContainer'>
                <img src='https://i.pinimg.com/originals/c9/64/5f/c9645fa432dd95836ee912a3af9156b6.png' alt="" />
            </div>
            <div class='productInfoContainer'>
                <a to='' class='productTitle'>Instrumento de percusión</a>
                <p class='productPrice'>$ 25000</p>
                <span class='productShipping free' v-if="costoEnvio === '0'"><img src={camion} alt="" /> Envío gratis a todo el país</span>
                <span class='productShipping non-free' v-else-if="costoEnvio !== '0'">Costo de envío Interior de Argentina: 100</span>
                <span class='productSoldOut'>25 vendidos</span>
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

