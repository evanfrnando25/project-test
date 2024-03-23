<template>
    <div class="main">
        <div class="wrapper">
            <div class="sidebar">
                <CommonSidebar />
            </div>
            <div class="content">
                <div class="content__wrapper">
                    <div class="content__header">
                        ini header
                    </div>
                    <div class="content__main">
                        <slot />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.main {

    .wrapper {
        display: grid;
        grid-template-columns: 15% 80%;
        gap: 5%;
    }

}

</style>