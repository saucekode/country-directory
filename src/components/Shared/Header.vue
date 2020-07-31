<template>
    <div class="d-flex header j-btw align-items" :class="mode">
        <h2>Where in the world?</h2>
        <Toggle 
        :mode="mode" 
        :modeIcon="modeIcon" 
        :modeText="modeText"
        @toggle="$emit('toggle')"/>
    </div>
</template>

<script>
    import Toggle from './Toggle';

    export default {
        name: 'Header',
        props: ['mode', 'modeIcon', 'modeText'],
        components: {
            Toggle
        }
    }
</script>

<style>
    .header{
        height: 80px;
        box-shadow: 0 0 6px rgba(0,0,0,0.3);
        padding: 0 55px;
        line-height: 75px;
        background: #fff;
        color: #192734;
        transition: all .3s ease-in-out;
    }

    .dark .header{
        background: hsl(209, 23%, 22%)
    }

    
</style>