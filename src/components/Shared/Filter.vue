<template>
    <div class="Filter cursor-point" :class="mode">
        <select id="Filter-Select">
            <option value="default">Filter by region</option>
            <option value="default">Africa</option>
            <option value="default">America</option>
            <option value="default">Asia</option>
            <option value="default">Europe</option>
            <option value="default">Oceania</option>
        </select>
    </div>
</template>

<script>
    export default{
        name: 'Filtersearch',
        props: ["mode"]
    }
</script>

<style>
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