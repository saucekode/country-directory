<template>
    <div>
        <div class="d-flex j-btw searchFilter">
            <div class="Search">
                <input type="search" placeholder="Search for a country..." v-model="filterCountry">
            </div>
            <div class="Filter cursor-point">
                <select id="Filter-Select">
                    <option value="default">Filter by region</option>
                    <option value="default">Africa</option>
                    <option value="default">America</option>
                    <option value="default">Asia</option>
                    <option value="default">Europe</option>
                    <option value="default">Oceania</option>
                </select>
            </div>
        </div>
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
    </div>
</template>

<script>
    import Country from '@/components/Shared/Country';
    import axios from 'axios';

    export default{
        data(){
            return{
                countryData: [],
                filterCountry: ''
            }
        },
        mounted(){
            axios({
                method: 'get',
                url: 'https://restcountries.eu/rest/v2/all'
            }).then(res => res.data.map(resData => {
                this.countryData.push(resData)
                
            })).catch(error => console.log(error))
            
        },
        computed:{
            searchCountries(){
                return this.countryData.filter(country => {
                    return country.name.toLowerCase().includes(this.filterCountry.toLowerCase())
                })
            }
        },
        name: 'Countries',
        
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
    .searchFilter{
        width: 1200px;
        margin: 0 auto;
    }
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
    .Filter #Filter-Select{
        width: 180px;
        height: 45px;
        background: #fff;
        border-radius: 4px;
        text-indent: 15px;
        box-shadow: 0 0 10px rgba(0,0,0,0.3);
        font-weight: 600;
        color: #192734;
    }

    .dark #Filter-Select{
        background: hsl(209, 23%, 22%);
        color: #fff
    }
</style>