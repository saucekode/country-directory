<template>
    <div class="Content" :class="mode">
        <div class="d-flex j-btw">
            <Search :mode="mode"/>
            <Filtersearch :mode="mode"/>
        </div>
        <Countries/>
    </div>
</template>

<script>
    import Search from '../Shared/Search'
    import Filtersearch from '../Shared/Filter'
    import Countries from '../Shared/Countries'

    export default{
        name: 'Content', 
        props: ['mode'],
        components: {
            Search,
            Filtersearch,
            Countries
        }
    }
</script>

<style>
    .Content{
        padding: 35px 55px;
        background: #f3f3f3;
        color: #192734;
        transition: all .3s ease-in-out;
    }

    .dark .Content *, .dark .Content{
        background-color: hsl(207, 26%, 17%);
        color: #fff;
    }
</style>