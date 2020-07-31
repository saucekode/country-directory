<template>
    <div class="d-flex j-btw Countries">
        <Country 
        v-for="country in countryData" 
        :key="country.numericCode"
        :nameCountry="country.name"
        :flag="country.flag"
        :population="country.population"
        :region="country.region"
        :capital="country.capital">{{country}}</Country>
    </div>
</template>

<script>
    import Country from '@/components/Shared/Country';
    import axios from 'axios';

    export default{
        data(){
            return{
                countryData: []
            }
        },
        created(){
            axios({
                method: 'get',
                url: 'https://restcountries.eu/rest/v2/all'
            }).then(res => res.data.map(resData => {
                this.countryData.push(resData)
            }))
        },
        name: 'Countries',
        methods: {

        },
        components: {
            Country
        }
    }
</script>
<style>

    .Countries{
        padding-top: 45px;
        margin: 0 auto;
        flex-wrap: wrap;
    }
</style>