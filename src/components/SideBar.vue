<template>
    <div>
        <aside>
            <div class="logo">
                <img src="../../public/favicon.ico" alt="logo" >
            </div>
            
        </aside>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>

aside{
    background-color: #1e293b;;
    display: flex;
    color:#f1f5f9;
    flex-direction: column;
    width: calc(2rem + 32px);
    min-height: 100vh;
    padding: 1rem;

    transition: .4s ease-out;
}

.logo{
    margin-bottom: 1rem;
}

img{
    width: 20px;
}
</style>