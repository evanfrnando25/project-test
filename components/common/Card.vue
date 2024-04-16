<template>
    <div class="card">
        <div class="card__wrapper">
            <slot />
        </div>
    </div>
</template>


<style lang="scss" scoped>

.card {
    width: 100%;
    background: #016DD3;
    color: #ffffff;
    padding: 2%;
    height: 100%;
    border-radius: 10px;

    @media (min-width: 1080px){}

    &__wrapper {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    
  
}
</style>