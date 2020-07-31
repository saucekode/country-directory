<template>
    <div class="Search" :class="mode">
        <input type="search" placeholder="Search for a country...">
    </div>
</template>

<script>
    export default{
        name: 'Search',
        props:["mode"],
        methods:{
            searchCountry(){
                
            }
        }
    }
</script>

<style>
    .Search input[type="search"]{
        width: 350px;
        height: 45px;
        background: #fff;
        padding: 2px 18px 0 0;
        border-radius: 4px;
        text-indent: 18px;
        box-shadow: 0 0 10px rgba(0,0,0,0.3);
        font-weight: 600;
    }

    .Search input[type="search"]::placeholder{
        font-family: 'Nunito Sans';
        font-weight: 600;
        color: #192734;
    }

    .dark .Search input[type="search"]{
        background: hsl(209, 23%, 22%);
        color: #fff;
    }

    .dark .Search input[type="search"]::placeholder{
        color: #fff
    }
</style>