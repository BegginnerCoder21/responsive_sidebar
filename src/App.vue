<script setup lang="ts">
import SideBar from './components/SideBar.vue';


</script>

<template>
    <div class="app">
        <side-bar />
        <router-view/>
    </div>
</template>

<style lang="scss">
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
 :rout{
    --primary:#4ade80;
    --primary-alt:#22c55e;
    --grey:#64748b;
    --dark:#1e293b;
    --dark-alt:#334155;
    --light:#f1f5f9;
    --sidebar-width:200px;
}

body{
    background-color: var(--light);
}
.app{
    display: flex;
    
} 
</style>
