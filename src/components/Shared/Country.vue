<template>
    <div>
        <transition enter-active-class="animated fadeInUp">
            <div class="Country">
                <div class="Country-flag">
                    <img :src="flag" :alt="nameCountry">
                </div>
                <div class="Country-details" :class="mode">
                    <h4 class="nunito-bold">{{nameCountry}}</h4>
                    <p>Population: <span>{{population}}</span></p>
                    <p>Region: <span>{{region}}</span></p>
                    <p>Capital: <span>{{capital}}</span></p>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
    export default{
        name: 'Country',
        props: ['mode', 'flag','nameCountry', 'population', 'region', 'capital']
    }
</script>

<style>
    .Country{
        height: 290px;
        width: 240px;
        margin: 32px 25px 30px 32px;
        cursor: pointer;
        background: transparent;
        box-shadow: 0 0 10px rgba(0,0,0,0.5)
    }
    .Country-flag{
        height: 140px;
    }
    .Country-flag img{
        height: 100%;
        width: 100%;
        object-fit: cover;
        border-top-right-radius: 5px;
        border-top-left-radius: 5px;
    }
    .Country-details{
        height: 150px;
        border-bottom-right-radius: 5px;
        border-bottom-left-radius: 5px;
        background: #fff;
        padding: 0 25px;
    }

    .Country-details h4{
        padding-top: 15px;
        font-size: 14px;
        font-weight: bold;
    }

    .Country-details p{
        margin-top: 7px;
        font-size: 15px;
        font-weight: 600;
    }

    .Country-details p span{
        font-weight: 100;
    }
</style>