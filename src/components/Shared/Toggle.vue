<template>
    <div class="d-flex align-items materials" :class="mode" @click="$emit('toggle')">
        <i :class="modeIcon"></i>
        <p :style="{marginLeft: 5 + 'px', fontWeight: 600, textTransform: 'capitalize'}">{{modeText}} Mode</p>
    </div>
</template>

<script>
    export default{
        name: 'Toggle', 
        props: ['mode','modeIcon','modeText']
    }
</script>

<style>
    .materials *{  
        color: #192734;
        cursor: pointer;
        transition: all .3s ease-in-out;
    }

    .dark .materials *{
        color:#fff
    }

</style>