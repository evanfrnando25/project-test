<template>
        <div class="sidebar__wrapper">
            <div class="siderbar__logo">
                ini logo
            </div>
            <div class="sidebar__navigation">
                <div class="sidebar__navigation__link">
                    <span>Home</span>
                </div>
            </div>
        </div>
</template>


<style lang="scss"scoped>

.sidebar {

    &__wrapper {
        display: flex;
        flex-direction: column;
        gap: 30px;
        background: red;
        height: 100vh;
    }

    &__navigation {
        display: flex;
        flex-direction: column;
        gap: 15px;
        padding: 5%;
        background: blue;
    }

}

</style>